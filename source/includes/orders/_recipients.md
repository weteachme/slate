## READ Order Recipients

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/123123/recipients"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders/123123/recipients",
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
      "type":"order/recipients",
      "attributes": {
        "firstname": "John",
        "lastname": "Snow",
        "email": "john@got.com",
        "code": "64533838",
        "delivery-date": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "order-id": "1231212"
      }
    }
  ]
}
```

This endpoint retrieves one order by id.

### HTTP Request

`GET https://api.weteachme.com/v1/orders/123123/recipients`

## Update Recipient By Id

```shell
curl -X PATCH 
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/recipients/12" 
  -d '{
    "data": {
      "id": 12,
      "type": "order/recipients",
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
    "type": "order/recipients",
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
  "https://api.weteachme.com/v1/orders/recipients/12", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);


```

> The above command returns HTTP/1.1 204

This endpoint updates one recipient by id.


### HTTP Request

`PATCH https://api.weteachme.com/v1/orders/recipients/123123`


## Send Recipient Gift Voucher Email

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/recipients/123123/gift-voucher-emails
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.post(
  "https://api.weteachme.com/v1/orders/recipients/123123/gift-voucher-emails
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
      "type":"gift-voucher-emails",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-emails/123123"
      },
      "relationships":{
         "payment-activity":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-emails/123123/relationships/recipient",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-emails/123123/recipient"
            }
         }
      }
   }
}
```


This endpoint sends gift-voucher email by payment activity id.

### HTTP Request

`POST https://api.weteachme.com/v1/orders/recipients/123123/gift-voucher-emails`


## Cancel Recipient Gift Voucher

```shell
curl 
  -X POST
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/recipients/123123/gift-voucher-cancellations"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.post(
  "https://api.weteachme.com/v1/orders/recipients/123123/gift-voucher-cancellations",
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
      "type":"gift-voucher-cancellations",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-cancellations/123123"
      },
      "relationships":{
         "payment-activity":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-cancellations/123123/relationships/recipient",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-cancellations/123123/recipient"
            }
         }
      }
   }
}
```

This endpoint cancels gift-voucher by id.

### HTTP Request

`POST https://api.weteachme.com/v1/orders/recipients/123123/gift-voucher-cancellations`
