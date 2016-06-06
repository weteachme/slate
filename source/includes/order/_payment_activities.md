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

This endpoint retrieves one order by id.

### HTTP Request

`GET https://api.weteachme.com/v1/order/payment-activities?filter[order-id]=1231212`

