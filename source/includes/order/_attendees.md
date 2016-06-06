## READ Order Attendees

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/order/attendees?filter[order-id]=1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/order/attendees?filter[order-id]=1231212", 
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
      "type":"order/attendees",
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
      "type":"order/attendees",
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
      "type":"order/attendees",
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

`GET https://api.weteachme.com/v1/order/attendees?filter[order-id]=1231212`

