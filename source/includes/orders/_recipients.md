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
      "type":"orders/recipients",
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

## Update Recipient Info

```shell
curl -X POST
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/recipients/12/recipient-infos" 
  -d '{
    "data": {
      "id": 12,
      "type": "orders/recipient-infos",
      "attributes": {
        "firstname": "Wayne",
        "lastname": "Rooney",
        "email": "wayne@rooney.com",
        "greeting": "Some Greeting"
      },
      "relationships":{
        "recipient":{
          "data":{
             "type": "orders/recipients",
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
    "id": 12,
    "type": "orders/recipient-infos",
    "attributes": {
      "firstname": "Wayne",
      "lastname": "Rooney",
      "email": "wayne@rooney.com",
      "greeting": "Some Greeting"
    },
    "relationships":{
      "recipient":{
        "data":{
           "type": "orders/recipients",
           "id": 12
        }
      }
    }
  }
}
HTTParty.post(
  "https://api.weteachme.com/v1/orders/recipients/12/recipient-infos", 
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
      "type": "orders/recipient-infos",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/recipient-infos/12"
      },
      "attributes": {
        "firstname": "Wayne",
        "lastname": "Rooney",
        "email": "wayne@rooney.com",
        "greeting": "Some Greetings",
      },
      "relationships":{
         "recipient":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/recipient-infos/123123/relationships/recipient",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/recipient-infos/123123/recipient"
            }
         }
      }
    }
}
```

This endpoint updates one recipient by id.

### Scenario

Steps      | Actions
---------- | -------
When | vendor updates recipient info
Then | recipient info is updated
Then | it logs the details updated activity


### HTTP Request

`POST https://api.weteachme.com/v1/orders/recipients/123123/recipient-infos`


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
      "type":"orders/gift-voucher-emails",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-emails/123123"
      },
      "relationships":{
         "recipient":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-emails/123123/relationships/recipient",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-emails/123123/recipient"
            }
         }
      }
   }
}
```

This endpoint sends gift voucher email by recipient id.

### Scenario

Steps      | Actions
---------- | -------
When | vendor sends gift voucher emails
Then | email should be send to the recipient
Then | it logs the send email activity

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
      "type":"orders/gift-voucher-cancellations",
      "links":{
         "self":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-cancellations/123123"
      },
      "relationships":{
         "recipient":{
            "links":{
               "self":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-cancellations/123123/relationships/recipient",
               "related":"http://api-dev.weteachme.com:3000/v1/orders/gift-voucher-cancellations/123123/recipient"
            }
         }
      }
   }
}
```

This endpoint cancels gift voucher by id.

### Scenario

Steps      | Actions
---------- | -------
When | vendor cancels gift voucher
Then | gift voucher is expired
Then | recipient is cancelled
Then | it logs the gift voucher cancelled activity

### HTTP Request

`POST https://api.weteachme.com/v1/orders/recipients/123123/gift-voucher-cancellations`
