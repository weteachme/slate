## READ Order Payment Activities

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/order/payment-activities?filter[order-id]=1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/order/payment-activities?filter[order-id]=1231212", 
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
      "type":"order/payment-activities",
      "attributes": {
        "type": "Payment",
        "name": "How to Make Coffee",
        "total": 120.00,
        "fee": 10.00,
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "payment-method": "Online",
        "status": "Paid",
        "due-date": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "order-id": 1231212
      }
    },
    {
      "id":"123",
      "type":"order/payment-activities",
      "attributes": {
        "type": "Refund",
        "name": "Refund",
        "total": 100.00,
        "fee": 0,
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "order-id": 1231212
      }
    }
  ]
}
```

This endpoint retrieves payment activities by order id.

### HTTP Request

`GET https://api.weteachme.com/v1/order/payment-activities?filter[order-id]=1231212`


## READ Order Payment Activity By Id

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/order/payment-activities/123123
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/order/payment-activities/123123
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
    "type":"order/payment-activities",
    "attributes": {
      "type": "Payment",
      "name": "How to Make Coffee",
      "total": 120.00,
      "fee": 10.00,
      "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "payment-method": "Online",
      "status": "Paid",
      "due-date": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "order-id": 1231212
    }
  }
}
```

This endpoint retrieves one payment activity by id.

### HTTP Request

`GET https://api.weteachme.com/v1/order/payment-activities/123123`


## Send Payment Confirmation Email

```shell
curl 
  -X PATCH
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/order/payment-activities/send-confirmation-email
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.patch(
  "https://api.weteachme.com/v1/order/payment-activities/123123/send-confirmation-email
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns no content with 204 HTTP Status


This endpoint sends reminder email by payment activity id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/order/payment-activities/123123/send-confirmation-email`


## Send Payment Reminder Email

```shell
curl 
  -X PATCH
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/order/payment-activities/send-reminder-email
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.patch(
  "https://api.weteachme.com/v1/order/payment-activities/123123/send-reminder-email
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns no content with 204 HTTP Status


This endpoint sends reminder email by payment activity id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/order/payment-activities/123123/send-reminder-email`

## Mark Payment as Paid

```shell
curl 
  -X PATCH
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/order/payment-activities/123123/mark-as-paid
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.patch(
  "https://api.weteachme.com/v1/order/payment-activities/123123/mark-as-paid
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns no content with 204 HTTP Status

This endpoint marks payment activity as paid by id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/order/payment-activities/123123/mark-as-paid`


## Cancel Payment

```shell
curl 
  -X PATCH
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/order/payment-activities/123123/cancel-payment
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.patch(
  "https://api.weteachme.com/v1/order/payment-activities/123123/cancel-payment
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns no content with 204 HTTP Status

This endpoint cancels payment by id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/order/payment-activities/123123/cancel-payment`
