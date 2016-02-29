# Merchandise

## READ All Merchandises

```shell
curl 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/merchandises"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/merchandises?page[number]=1&page[size]=20", 
  headers: {
    "Accept" => "application/vnd.api+json",
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
      "type":"merchandises",
      "links":{"self":"/v1/merchandises/224476"},
      "attributes": {
        "name": "Coffee Beans",
        "price": 30.00,
        "currency": "AUD",
        "stock": 1000,
        "sold": 10
      }
    }
  ]
}
```

This endpoint retrieves all merchandises.

### HTTP Request

`GET https://api.weteachme.com/v1/merchandises`

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
name          | string     |  
min-price     | number     |  
max-price     | number     |  

### Sorting Fields

Parameter  | Example
---------- | -----------
name  | datetime | -datetime
price | price | -price
sold  | sold | -sold


## READ Merchandise

```shell
curl 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/merchandises/1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/merchandises/1231212", 
  headers: {
    "Accept" => "application/vnd.api+json",
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id":"224476",
    "type":"merchandises",
    "links":{"self":"/v1/merchandises/224476"},
    "attributes": {
      "name": "Coffee Beans",
      "price": 30.00,
      "currency": "AUD",
      "stock": 1000,
      "sold": 10
    }
  },
  "included": [{
    "type": "classes",
    "id": "1",
    "attributes": {
      "name": "Painting Class"
    }
  }]
}
```

This endpoint retrieves one merchandise by id.

### HTTP Request

`GET https://api.weteachme.com/v1/merchandisess`


## CREATE Merchandise

```shell
curl -X POST
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/merchandises" 
  -d '{
    "data": {
      "type": "merchandises",
      "attributes": {
        "name": "Coffee Beans",
        "price": 30.00,
        "currency": "AUD",
        "stock": 1000
      },
      "relationships": {
        "classes": {
          "data": [
            { "type": "class", "id": "9" },
            { "type": "class", "id": "10" }
          ]
        }
      }
    }
  }'
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

payload = {
  "data": {
    "type": "merchandises",
    "attributes": {
      "name": "Coffee Beans",
      "price": 30.00,
      "currency": "AUD",
      "stock": 1000
    },
    "relationships": {
      "classes": {
        "data": [
          { "type": "class", "id": "9" },
          { "type": "class", "id": "10" }
        ]
      }
    }
  }
}
HTTParty.post(
  "https://api.weteachme.com/v1/merchandises", 
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
    "type":"merchandises",
    "links":{
      "self":"/v1/merchandises/224476"
    },
    "attributes": {
      "name": "Coffee Beans",
      "price": 30.00,
      "currency": "AUD",
      "stock": 1000,
      "sold": 0
    }
  },
  "included": [{
    "type": "classes",
    "id": "9",
    "attributes": {
      "name": "Painting Class"
    }
  },
  {
    "type": "classes",
    "id": "10",
    "attributes": {
      "name": "Coffee Making Class"
    }
  }]
}
```

This endpoint creates one merchandise.

### HTTP Request

`POST https://api.weteachme.com/v1/merchandises`


## UPDATE Merchandise

```shell
curl -X PATCH 
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/merchandises/12" 
  -d '{
    "data": {
      "id": 12,
      "type": "merchandises",
      "attributes": {
        "name": "Coffee Beans",
        "price": 40.00
      },
      "relationships": {
        "classes": {
          "data": [
            { "type": "class", "id": "8" },
            { "type": "class", "id": "10" }
          ]
        }
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
    "type": "merchandises",
    "attributes": {
      "name": "Coffee Beans",
      "price": 40.00,
      "currency": "AUD",
      "stock": 1000
    }
  }
}
HTTParty.patch(
  "https://api.weteachme.com/v1/merchandises/12", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one merchandise by id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/merchandises/12`

## DELETE Merchandise

```shell
curl -X DELETE 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/merchandises/12" 
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.delete(
  "https://api.weteachme.com/v1/merchandises/12", 
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => 'meowmeowmeow'"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one merchandise by id.

### HTTP Request

`DELETE https://api.weteachme.com/v1/merchandises/12`
