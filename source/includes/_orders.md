# Orders

## GET All Orders

```shell
curl "https://api.weteachme.com/v1/orders"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders?page[number]=1&page[size]=20", 
  headers: {"API-KEY" => meowmeowmeow"}
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


## GET Order

```shell
curl "https://api.weteachme.com/v1/orders/1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders/1231212", 
  headers: {"API-KEY" => meowmeowmeow"}
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
      "billing-name": "Edward Kelly",
      "billing-email": "edward@kelly.com",
      "order-id": 10114818,
      "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "amount": 160.95,
      "currency": "AUD",
      "status": "Paid"
    }
  },
  "included": [{
    "type": "carts",
    "id": "1",
    "attributes": {
      "name": "Painting Class"
    },
    "included": [{
      "type": "attendees",
      "id": "100",
      "attributes": {
        "name": "Edward Keylly",
        "email": "edward@email.com"
      }
    }]
  }]
}
```

This endpoint retrieves one order by id.

### HTTP Request

`GET https://api.weteachme.com/v1/orders/1231212`
