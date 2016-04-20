# Classes

## READ All Classes

```shell
curl 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/classes"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/classes?page[number]=1&page[size]=20&include=dates&fields[classes]=name,location,thumbnail", 
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
      "type":"classes",
      "links":{"self":"/v1/classes/224476"},
      "attributes": {
        "name": "How to Make Coffee Beans",
        "location": "41 Steward St, Richmond, VIC 3121",
        "thumbnail": "https://some-dns-hosted.com/url/thumbnail.jpg"
      }
    }
  ]
}
```

This endpoint retrieves all classes.

### HTTP Request

`GET https://api.weteachme.com/v1/classes`

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

### Sorting Fields

Parameter  | Example
---------- | -----------
name  | name | -name


## READ Class

```shell
curl 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/classes/1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/classes/1231212", 
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
    "type":"classes",
    "links":{"self":"/v1/classes/224476"},
    "attributes": {
      "name": "How to Make Coffee Beans",
      "location": "41 Steward St, Richmond, VIC 3121",
      "thumbnail": "https://some-dns-hosted.com/url/thumbnail.jpg",
      "category_id": 121,
      "subcategory_id": 133,
      "all the fields": "..."
    }
  }
}
```

This endpoint retrieves one class by id.

### HTTP Request

`GET https://api.weteachme.com/v1/class/1212`


## CREATE Class

```shell
curl -X POST
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/classes" 
  -d '{
    "data": {
      "type": "classes",
      "attributes": {
        "name": "How to Make Coffee Beans",
        "location": "41 Steward St, Richmond, VIC 3121",
        "thumbnail": "https://some-dns-hosted.com/url/thumbnail.jpg",
        "category_id": 121,
        "subcategory_id": 133,
        "all updatable fields": "..."
      }
    }
  }'
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

payload = {
  "data": {
    "type": "classes",
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
HTTParty.post(
  "https://api.weteachme.com/v1/classes", 
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
    "type":"classes",
    "links":{
      "self":"/v1/classes/224476"
    },
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
```

This endpoint creates one class.

### HTTP Request

`POST https://api.weteachme.com/v1/classes`


## UPDATE Class

```shell
curl -X PATCH 
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/classes/12" 
  -d '{
    "data": {
      "id": 12,
      "type": "classes",
      "attributes": {
        "name": "How to Make Coffee Beans",
        "location": "41 Steward St, Richmond, VIC 3121",
        "thumbnail": "https://some-dns-hosted.com/url/thumbnail.jpg",
        "category_id": 121,
        "subcategory_id": 133,
        "all updatable fields": "..."
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
    "type": "classes",
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
  "https://api.weteachme.com/v1/classes/12", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one class by id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/classes/12`

## DELETE Class

```shell
curl -X DELETE 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/classes/12" 
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.delete(
  "https://api.weteachme.com/v1/classes/12", 
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => 'meowmeowmeow'"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one class by id.

### HTTP Request

`DELETE https://api.weteachme.com/v1/classes/12`
