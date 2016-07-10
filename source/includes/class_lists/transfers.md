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

### HTTP Request

`POST https://api.weteachme.com/v1/class-lists/123123/transfers`
