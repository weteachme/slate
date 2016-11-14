## Cancel Class

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/class-lists/123123/class-cancellations
  -d '{
    "data": {
      "type": "class-lists/cancellations",
      "attributes": {
        "subject": "Class Cancellation Notification",
        "body": "<p>Welcome to the class, bla...bla...</p>"
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
    "type": "class-lists/cancellations",
    "attributes": {
      "subject": "Class Cancellation Notification",
      "body": "<p>Welcome to the class, bla...bla...</p>"
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
  "https://api.weteachme.com/v1/class-lists/123123/class-cancellations",
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
      "type":"class-lists/cancellations",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/class-lists/class-cancellations/123123"
      },
      "relationships":{
         "class-list":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/class-lists/class-cancellations/123123/relationships/class-list",
               "related":"http://api-dev.weteachme.com:3000/v1/class-lists/class-cancellations/123123/class-list"
            }
         }
      }
   }
}
```

This endpoint cancels class and sends cancellation emails to class attendees.

### Scenario

Steps      | Actions
---------- | -------
When | Vendor cancels class
Then | cancelled attribute should set to true for the class date
Then | it sends out cancellation emails
Then | it logs the class cancellation activity


### HTTP Request

`POST https://api.weteachme.com/v1/class-lists/123123/class-cancellations`