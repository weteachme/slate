# Merchandise

## GET All Merchandises

```shell
curl "https://api.weteachme.com/v1/merchandises"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/merchandises?page[number]=1&page[size]=20", 
  headers: {"API-KEY" => meowmeowmeow"}
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


## GET Merchandise

```shell
curl "https://api.weteachme.com/v1/merchandises/1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/merchandises/1231212", 
  headers: {"API-KEY" => meowmeowmeow"}
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

`GET https://api.weteachme.com/v1/merchandises/1231212`
