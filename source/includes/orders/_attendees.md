## READ Order Attendees

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/1231212/attendees"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders/1231212/attendees",
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id":"123",
      "type":"orders/attendees",
      "attributes": {
        "firstname": "John",
        "lastname": "Snow",
        "email": "john@got.com",
        "ticket-name": "Normal Price",
        "class-date": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "class-name": "How to Revive From Dead",
        "order-id": 1231212
      }
    }
  ]
}
```

This endpoint retrieves attendees by order id.

### HTTP Request

`GET https://api.weteachme.com/v1/orders/1231212/attendees`

## READ Order Attendee By Id

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/attendees/123123
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders/attendees/123123
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id":"123",
    "type":"orders/attendees",
    "attributes": {
      "firstname": "John",
      "lastname": "Snow",
      "email": "john@got.com",
      "salutation": "Mr.",
      "gender": "Female",
      "dob": "12/12/1999",
      "age": "20",
      "company": "Company Name",
      "companyTitle": "Brand Manager",
      "address": "35 Nice Road, Melbourne",
      "postcode": "3000",
      "suburb": "Melbourne",
      "member-id": "2323333",
      "deal-code": "232xedke9",
      "security-code": "23423ldld",
      "uniform-size": "10",
      "emergency-contact": "Some one \r\n 0433 333 333",
      "medical": "N/A",
      "requirment": "None",
      "field-list": {
        "salutation": true,
        "age": true
      },
      "ticket-name": "Normal Price",
      "class-date": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "class-name": "How to Revive From Dead",
      "order-id": 1231212
    }
  }
}
```

This endpoint retrieves one attendee by id.

### HTTP Request

`GET https://api.weteachme.com/v1/orders/attendees/123123`

## Update Attendee Info

```shell
curl -X POST
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/attendees/12/attendee-infos" 
  -d '{
    "data": {
      "type": "orders/attendee-infos",
      "attributes": {
        "firstname": "Wayne",
        "lastname": "Rooney",
        "email": "wayne@rooney.com",
        "mobile": "0433 333 333",
        "requirements": "Gluten Free",
        "medical": "None",
        "emergency-contact": "Some Contacts",
        "all updatable fields": "..."
      },
      "relationships":{
        "attendee":{
          "data":{
             "type": "orders/attendees",
             "id": 12
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
    "type": "orders/attendee-infos",
    "attributes": {
      "firstname": "Wayne",
      "lastname": "Rooney",
      "email": "wayne@rooney.com",
      "mobile": "0433 333 333",
      "requirements": "Gluten Free",
      "medical": "None",
      "emergency_contact": "Some Contacts",
      "all updatable fields": "..."
    },
    "relationships":{
      "attendee":{
        "data":{
           "type": "orders/attendees",
           "id": 12
        }
      }
    }
  }
}
HTTParty.post(
  "https://api.weteachme.com/v1/orders/attendees/12/attendee-infos", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);


```

> The above command returns JSON structured like this:

```json
{
    "data": {
      "id": 12,
      "type": "orders/attendee-infos",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/attendee-infos/12"
      },
      "attributes": {
        "firstname": "Wayne",
        "lastname": "Rooney",
        "email": "wayne@rooney.com",
        "mobile": "0433 333 333",
        "requirements": "Gluten Free",
        "medical": "None",
        "emergency-contact": "Some Contacts",
        "all updatable fields": "..."
      },
      "relationships":{
         "attendee":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/attendee-infos/123123/relationships/attendee",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/attendee-infos/123123/attendee"
            }
         }
      }
    }
}
```

This endpoint updates one attendee by id.

### Scenario

Steps      | Actions
---------- | -------
When | vendor updates attendee info
Then | all applicable fields are updated
Then | it logs the details updated activity


### HTTP Request

`POST https://api.weteachme.com/v1/orders/attendees/12/attendee-infos`


## Send Attendee Enrolment Email

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/attendees/123123/enrolment-emails
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.post(
  "https://api.weteachme.com/v1/orders/attendees/123123/enrolment-emails
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
      "type":"orders/enrolment-emails",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/enrolment-emails/123123"
      },
      "relationships":{
         "attendee":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/enrolment-emails/123123/relationships/attendee",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/enrolment-emails/123123/attendee"
            }
         }
      }
   }
}
```

This endpoint sends enrolment email by attendee id.

### Scenario

Steps      | Actions
---------- | -------
When | vendor sends enrolment emails 
Then | email is sent to the attendee
Then | it logs the send email activity

### HTTP Request

`POST https://api.weteachme.com/v1/orders/attendees/123123/enrolment-emails`


## Cancel Attendee Spot

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/attendees/123123/spot-cancellations"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.post(
  "https://api.weteachme.com/v1/orders/attendees/123123/spot-cancellations",
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
      "type":"orders/spot-cancellations",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/spot-cancellations/123123"
      },
      "relationships":{
         "attendee":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/spot-cancellations/123123/relationships/attendee",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/spot-cancellations/123123/attendee"
            }
         }
      }
   }
}
```

This endpoint cancels spot by id.

### Scenario

Steps      | Actions
---------- | -------
When | vendor cancels attendee spot
Then | attendee is cancelled for the class
Then | it logs the spot cancelled activity


### HTTP Request

`POST https://api.weteachme.com/v1/orders/attendees/123123/spot-cancellations`
