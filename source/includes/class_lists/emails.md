## Send Class Email

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/class-lists/123123/class-emails
  -d '{
    "data": {
      "type": "class-lists/class-emails",
      "attributes": {
        "subject": "Class Cancellation Notification",
        "body": "<p>Welcome to the class, bla...bla...</p>",
        "send-to": "all"
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
    "type": "class-lists/class-emails",
    "attributes": {
      "subject": "Class Cancellation Notification",
      "body": "<p>Welcome to the class, bla...bla...</p>",
      "send-to": "all"
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
  "https://api.weteachme.com/v1/class-lists/123123/class-emails",
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
      "type":"class-lists/class-emails",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/class-lists/class-emails/123123"
      },
      "relationships":{
         "class-list":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/class-lists/class-emails/123123/relationships/class-list",
               "related":"http://api-dev.weteachme.com:3000/v1/class-lists/class-emails/123123/class-list"
            }
         }
      }
   }
}
```

This endpoint sends emails to class attendees.

### Scenario

Steps      | Actions
---------- | -------
When | vendor sends emails 
Then | email should be send to all students in the list
Then | it logs the send email activity

### HTTP Request

`POST https://api.weteachme.com/v1/class-lists/123123/class-emails`
