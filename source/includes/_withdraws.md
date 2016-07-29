# Withdraw Funds

## CREATE Withdraw

```shell
curl -X POST
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/withdraws" 
  -d '{
    "data": {
      "type": "withdraws",
      "attributes": {
        "total": 100
      }
    }
  }'
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

payload = {
  "data": {
    "type": "withdraws",
    "attributes": {
      "total": "100"
    }
  }
}
HTTParty.post(
  "https://api.weteachme.com/v1/withdraws", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
    }
  );

```

> The above command returns HTTP/1.1 201 Created

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id":"224476",
    "type":"withdraws",
    "links":{
      "self":"/v1/withdraws/224476"
    },
    "attributes": {
      "total": 100 
    }
  }
}
```

This endpoint creates one withdraw.

### HTTP Request

`POST https://api.weteachme.com/v1/withdraws`
