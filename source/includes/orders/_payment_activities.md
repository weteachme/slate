## READ Order Payment Activities

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/1231212/payment-activities"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders/1231212/payment-activities",
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
      "type":"orders/payment-activities",
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
      "type":"orders/payment-activities",
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

`GET https://api.weteachme.com/v1/orders/1231212/payment-activities`


## READ Order Payment Activity By Id

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/payment-activities/123123"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders/payment-activities/123123",
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
    "type":"orders/payment-activities",
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

`GET https://api.weteachme.com/v1/orders/payment-activities/123123`


## Adjust Payment Details

```shell
curl -X POST
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/payment-activities/123123/payment-adjustments" 
  -d '{
    "data": {
      "id": 12,
      "type": "orders/payment-activities",
      "attributes": {
        "total": 122.30,
        "due-date": "12/12/2016",
        "note": "this is some note"
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
    "type": "orders/payment-activities",
    "attributes": {
      "total": 122.30,
      "due-date": "12/12/2016",
      "note": "this is some note"
    }
  }
}
HTTParty.post(
  "https://api.weteachme.com/v1/orders/payment-activities/123123/payment-adjustments", 
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
   "data":{
      "id":"123123",
      "type":"orders/payment-adjustments",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/payment-adjustments/123123"
      },
      "attributes":{
         "total":40.0,
         "due-date":"2017-02-01T00:00:00.000+00:00",
         "note": "this is some note"
      },
      "relationships":{
         "payment-activity":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/payment-adjustments/123123/relationships/payment-activity",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/payment-adjustments/123123/payment-activity"
            }
         }
      }
   }
}
```


This endpoint adjust payment by id.

### HTTP Request

`POST https://api.weteachme.com/v1/orders/payment-activities/123123/payment-adjustments`


## Send Payment Confirmation Email

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/payment-activities/123123/payment-confirmation-emails"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.post(
  "https://api.weteachme.com/v1/orders/payment-activities/123123/payment-confirmation-emails",
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
      "type":"orders/payment-confirmation-emails",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/payment-confirmation-emails/123123"
      },
      "relationships":{
         "payment-activity":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/payment-confirmation-emails/123123/relationships/payment-activity",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/payment-confirmation-emails/123123/payment-activity"
            }
         }
      }
   }
}
```

This endpoint sends confirmation email by payment activity id.

## Send Payment Reminder Email

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/payment-activities/123123/payment-reminder-emails"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.post(
  "https://api.weteachme.com/v1/orders/payment-activities/123123/payment-reminder-emails",
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
      "type":"orders/payment-reminder-emails",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/payment-reminder-emails/123123"
      },
      "relationships":{
         "payment-activity":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/payment-reminder-emails/123123/relationships/payment-activity",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/payment-reminder-emails/123123/payment-activity"
            }
         }
      }
   }
}
```

This endpoint sends reminder email by payment activity id.

### HTTP Request

`POST https://api.weteachme.com/v1/orders/payment-activities/123123/payment-reminder-emails`

## Mark Payment as Paid

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/payment-activities/123123/offline-payments"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.post(
  "https://api.weteachme.com/v1/orders/payment-activities/123123/offline-payments",
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
      "type":"orders/offline-payments",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/offline-payments/123123"
      },
      "relationships":{
         "payment-activity":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/offline-payments/123123/relationships/payment-activity",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/offline-payments/123123/payment-activity"
            }
         }
      }
   }
}
```

This endpoint marks payment activity as paid by id.

### HTTP Request

`POST https://api.weteachme.com/v1/orders/payment-activities/123123/offline-payments`


## Cancel Payment

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/payment-activities/123123/payment-cancellations"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.post(
  "https://api.weteachme.com/v1/orders/payment-activities/123123/payment-cancellations",
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
      "type":"orders/payment-cancellations",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/payment-cancellations/123123"
      },
      "relationships":{
         "payment-activity":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/payment-cancellations/123123/relationships/payment-activity",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/payment-cancellations/123123/payment-activity"
            }
         }
      }
   }
}
```

This endpoint cancels payment by id.

### HTTP Request

`POST https://api.weteachme.com/v1/orders/payment-activities/123123/payment-cancellations`
