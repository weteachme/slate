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
      "type":"order/attendees",
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
    "type":"order/attendees",
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
}
```

This endpoint retrieves one payment activity by id.

### HTTP Request

`GET https://api.weteachme.com/v1/orders/attendees/123123`

## Update Attendee By Id

```shell
curl -X PATCH 
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/attendees/12" 
  -d '{
    "data": {
      "id": 12,
      "type": "order/attendees",
      "attributes": {
        "firstname": "Wayne",
        "lastname": "Rooney",
        "email": "wayne@rooney.com",
        "mobile": "0433 333 333",
        "requirements": "Gluten Free",
        "medical": "None",
        "emergency_contact": "Some Contacts",
        "all updatable fields": "..."
      }
    }
  }'
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

payload = {
  "data": {
    "id": 12,
    "type": "order/attendees",
    "attributes": {
      "firstname": "Wayne",
      "lastname": "Rooney",
      "email": "wayne@rooney.com",
      "mobile": "0433 333 333",
      "requirements": "Gluten Free",
      "medical": "None",
      "emergency_contact": "Some Contacts",
      "all updatable fields": "..."
    }
  }
}
HTTParty.patch(
  "https://api.weteachme.com/v1/orders/attendees/12", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);


```

> The above command returns HTTP/1.1 200

This endpoint updates one attendee by id.


### HTTP Request

`PATCH https://api.weteachme.com/v1/orders/attendees/123123`


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

> The above command returns HTTP/1.1 200


This endpoint sends enrolment email by payment activity id.

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

> The above command returns HTTP/1.1 200

This endpoint cancels spot by id.

### HTTP Request

`POST https://api.weteachme.com/v1/orders/attendees/123123/spot-cancellations`
