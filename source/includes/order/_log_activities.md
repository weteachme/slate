## READ Order Log Activities

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/order/log-activities?filter[order-id]=1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/order/log-activities?filter[order-id]=1231212", 
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
      "type":"order/log-activities",
      "attributes": {
        "type": "Payment Updated",
        "who": "John Snow",
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "description": "John Snow updated payment #321",
        "additional-data": {

        },
        "order-id": 1231212
      }
    }
  ]
}
```

This endpoint retrieves one order by id.

### HTTP Request

`GET https://api.weteachme.com/v1/order/log-activities?filter[order-id]=1231212`

