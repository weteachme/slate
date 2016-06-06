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
        "firstname": "John",
        "lastname": "Snow",
        "email": "john@got.com",
        "ticket-name": "Normal Price",
        "class-date": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "class-name": "How to Revive From Dead",
        "order-id": 1231212
      }
    }
  ]
}
```

This endpoint retrieves one order by id.

### HTTP Request

`GET https://api.weteachme.com/v1/order/attendees?filter[order-id]=1231212`

