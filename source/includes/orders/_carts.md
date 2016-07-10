## READ Order Carts

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/orders/1231212/carts"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/orders/1231212/carts",
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
      "type":"orders/carts",
      "attributes": {
        "type": "Ticket",
        "name": "How to Make Coffee",
        "price": 120.00,
        "qty": 2,
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "ticket": "Normal Ticket"
      }
    },
    {
      "id":"123",
      "type":"orders/carts",
      "attributes": {
        "type": "Ticket",
        "name": "How to Make Coffee",
        "price": 100.00,
        "qty": 1,
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "ticket": "Early Bird"
      }
    },
    {
      "id":"124",
      "type":"orders/carts",
      "attributes": {
        "type": "Gift Voucher",
        "name": "How to Make Coffee",
        "price": 100.00,
        "qty": 1,
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)"
      }
    },
    {
      "id":"125",
      "type":"orders/carts",
      "attributes": {
        "type": "Merchandise",
        "name": "Coffee Beans",
        "price": 100.00,
        "qty": 3,
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)"
      }
    }
  ]
}
```

This endpoint retrieves one order by id.

### HTTP Request

`GET https://api.weteachme.com/v1/orders/1231212/carts`

