# Transactions

## GET All Transactions

```shell
curl "https://api.weteachme.com/v1/transactions"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/transactions?page[number]=1&page[size]=20", 
  headers: {"API-KEY" => meowmeowmeow"}
  );

```

> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id":"224476",
      "type":"transactions",
      "links":{"self":"/v1/transactions/224476"},
      "attributes": {
        "order-id": 10114818,
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "amount": 160.95,
        "balance": 1650.00,
        "currency": "AUD",
        "transaction-type":"Online",
        "detail": "1st Instalment"
      }
    }
  ]
}
```

This endpoint retrieves all transactions.

### HTTP Request

`GET https://api.weteachme.com/v1/transactions`

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
type          | string     |  Transaction Type (Online, Offline, Withdraw, Subscription, Adjustment)
order-id      | number     |  Order Id

### Sorting Fields

Parameter  | Example
---------- | -----------
datetime   | datetime | -datetime
amount     | amount | -amount
