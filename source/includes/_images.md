# Images

## CREATE Image

```shell
curl -X POST
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/images" 
  -d '{
    "data": {
      "type": "images",
      "attributes": {
        "name": "Nice Image",
        "url": "File Object"
      }
    },
    "relationships": {
      "class": {
        "data": { "type": "class", "id": "9" }
      }
    }
  }'
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

payload = {
  "data": {
    "type": "images",
    "attributes": {
      "name": "Nice Image",
      "url": "File Object"
    }
  },
  "relationships": {
    "class": {
      "data": { "type": "class", "id": "9" }
    }
  }
}
HTTParty.post(
  "https://api.weteachme.com/v1/images", 
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
    "type":"images",
    "links":{
      "self":"/v1/images/224476"
    },
    "attributes": {
      "name": "Nice Image",
      "url": "File Object"
    }
  },
  "relationships": {
    "class": {
      "data": { "type": "class", "id": "9" }
    }
  }
}
```

This endpoint creates one image.

### HTTP Request

`POST https://api.weteachme.com/v1/images`

<aside class="notice">
You must specify a <code>class relationship</code>.
</aside>

## UPDATE Image

```shell
curl -X PATCH 
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/images/12" 
  -d '{
    "data": {
      "id": 12,
      "type": "images",
      "attributes": {
        "name": "Nice Image",
        "url": "File Object"
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
    "type": "images",
    "attributes": {
      "name": "How to Make Coffee Beans",
      "location": "41 Steward St, Richmond, VIC 3121",
      "thumbnail": "https://some-dns-hosted.com/url/thumbnail.jpg",
      "category_id": 121,
      "subcategory_id": 133,
      "all updatable fields": "..."
    }
  }
}
HTTParty.patch(
  "https://api.weteachme.com/v1/images/12", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one image by id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/images/12`

## DELETE Image

```shell
curl -X DELETE 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/images/12" 
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.delete(
  "https://api.weteachme.com/v1/images/12", 
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => 'meowmeowmeow'"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one image by id.

### HTTP Request

`DELETE https://api.weteachme.com/v1/images/12`
