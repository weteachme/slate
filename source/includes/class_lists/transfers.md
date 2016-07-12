## Transfer Class

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/class-lists/123123/transfers
  -d '{
    "data": {
      "type": "class-lists/transfers",
      "attributes": {
        "attendee-ids": [1,2,3,4,5]
      },
      "relationships":{
        "class-list":{
          "data":{
             "type": "class-lists",
             "id": 123123
          }
        }
      }
    }
  }'
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

payload = {
  "data": {
    "type": "class-lists/transfers",
    "attributes": {
      "attendee-ids": [1,2,3,4,5]
    },
    "relationships":{
      "class-list":{
        "data":{
           "type": "class-lists",
           "id": 123123
        }
      }
    }
  }
}

HTTParty.post(
  "https://api.weteachme.com/v1/class-lists/123123/transfers",
  payload,
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns JSON structured like this:

```json
{
   "data":{
      "id": 123123,
      "type":"class-lists/transfers",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/class-lists/transfers/123123"
      },
      "relationships":{
         "class-list":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/class-lists/transfers/123123/relationships/class-list",
               "related":"http://api-dev.weteachme.com:3000/v1/class-lists/transfers/123123/class-list"
            }
         }
      }
   }
}
```

This endpoint transfers attendees.

### Scenario 1 - Transfer to same date (no merchandise)

Steps      | Actions
---------- | -------
When | vendor transfers all selected attendees to a different ticket within the same class date
Then | a transfer record is created for each attendee
Then | attendee is switched to another ticket
Then | an immediate due-now payment is generated for the transfer
Then | it processes payment only if requested by vendor
Then | it sends transfer email
Then | it logs the transfer activity

### Scenario 2 - Transfer to different date

Steps      | Actions
---------- | -------
When | vendor transfers all selected attendees to a different class date
Then | a transfer record is created for each attendee
Then | it makes sure the new date is not sold out
Then | it finds or creates the new cart for the new class date
Then | attendee is swtiched to the new cart
Then | new cart is set as completed
Then | linked merchandise for the previous date is moved to the new date
Then | an immediate due-now payment is generated for the transfer
Then | it processes payment only if requested by vendor
Then | it sends transfer email
Then | it logs the transfer activity

### Scenario 3 - Transfer with merchandise

Steps      | Actions
---------- | -------
When | transfer is completed
Then | merchandise is attached to the new date
Then | recurring payments for merchandise are also generated


### HTTP Request

`POST https://api.weteachme.com/v1/class-lists/123123/transfers`
