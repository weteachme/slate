# Orders

## READ All Orders

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders?page[number]=1&page[size]=20", 
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id":"224476",
      "type":"orders",
      "links":{"self":"/v1/orders/224476"},
      "attributes": {
        "billing-name": "Edward Kelly",
        "billing-email": "edward@kelly.com",
        "order-id": 10114818,
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "amount": 160.95,
        "currency": "AUD",
        "status":"Paid"
      }
    }
  ]
}
```

This endpoint retrieves all orders.

### HTTP Request

`GET https://api.weteachme.com/v1/orders`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
page      |          |         | [Pagination (http://jsonapi.org/format/#fetching-pagination)](http://jsonapi.org/format/#fetching-pagination)
filter    |          |         | [Filtering (http://jsonapi.org/format/#fetching-filtering)](http://jsonapi.org/format/#fetching-filtering)
sort      |          |         | [Sorting (http://jsonapi.org/format/#fetching-sorting)](http://jsonapi.org/format/#fetching-sorting)

### Pagination Fields

Parameter  | Description
---------- | -----------
size       | Maximum 50
number     | Default 1

### Filtering Fields

Parameter     | Type       |  Description
------------- | ---------- |  -----------
min-date      | string     |  dd/mm/yyyy
max-date      | string     |  dd/mm/yyyy
min-amount    | number     |  
max-amount    | number     |  
status        | string     |  Order Type (Online, Offline)
billing-email | string     |  Billing Email
billing-name  | string     |  Billing Name
order-id      | number     |  Order Id

### Sorting Fields

Parameter  | Example
---------- | -----------
datetime   | datetime | -datetime
amount     | amount | -amount


## READ an Order

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders/1231212", 
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
    "id":"224476",
    "type":"orders",
    "links":{"self":"/v1/orders/224476"},
    "attributes": {
      "billing-firstname": "Edward",
      "billing-lastname": "Kelly",
      "billing-email": "edward@kelly.com",
      "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "amount-paid": "299.00",
      "amount-outstanding": "99.00",
      "amount-earned": 280.00,
      "payment-method": "Online",
      "reference": "224476",
      "multi-classes": false,
      "multi-dates": false,
      "multi-ticket-types": true
    }
  },
  "relationships": {
    "carts": {
      "links": {
        "related": "https://api.weteachme.com/v1/order/carts?filter[order-id]=224476"
      }
    },
    "attendees": {
      "links": {
        "related": "https://api.weteachme.com/v1/order/attendees?filter[order-id]=224476"
      }
    },
    "recipients": {
      "links": {
        "related": "https://api.weteachme.com/v1/order/recipients?filter[order-id]=224476"
      }
    },
    "payment-activities": {
      "links": {
        "related": "https://api.weteachme.com/v1/order/payment-activities?filter[order-id]=224476"
      }
    },
    "log-activities": {
      "links": {
        "related": "https://api.weteachme.com/v1/order/log-activities?filter[order-id]=224476"
      }
    }
  }
}
```

This endpoint retrieves one order by id.

### HTTP Request

`GET https://api.weteachme.com/v1/orders/1231212`

## Update Order By Id

```shell
curl -X PATCH 
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/12123" 
  -d '{
    "data": {
      "id": 12,
      "type": "orders",
      "attributes": {
        "billing-firstname": "Wayne",
        "billing-lastname": "Rooney",
        "billing-email": "wayne@rooney.com"
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
    "type": "orders",
    "attributes": {
      "billing-firstname": "Wayne",
      "billing-lastname": "Rooney",
      "billing-email": "wayne@rooney.com"
    }
  }
}
HTTParty.patch(
  "https://api.weteachme.com/v1/orders/123123", 
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

`PATCH https://api.weteachme.com/v1/orders/123123`
