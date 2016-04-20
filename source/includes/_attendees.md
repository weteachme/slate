# Attendees

## READ All Attendees

```shell
curl 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/attendees"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/attendees?page[number]=1&page[size]=20&include=dates&fields[attendees]=name,location,thumbnail", 
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
      "type":"attendees",
      "links":{"self":"/v1/attendees/224476"},
      "attributes": {
        "name": "How to Make Coffee Beans",
        "location": "41 Steward St, Richmond, VIC 3121",
        "thumbnail": "https://some-dns-hosted.com/url/thumbnail.jpg"
      }
    }
  ]
}
```

This endpoint retrieves all attendees.

### HTTP Request

`GET https://api.weteachme.com/v1/attendees`

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
class-list-id | number     |  same as date-id
date-id       | number     |  same as above

### Sorting Fields

Parameter  | Example
---------- | -----------
name  | name | -name


## READ Attendee

```shell
curl 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/attendees/1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/attendees/1231212", 
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
    "type":"attendees",
    "links":{"self":"/v1/attendees/224476"},
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

This endpoint retrieves one attendee by id.

### HTTP Request

`GET https://api.weteachme.com/v1/attendee/1212`


## UPDATE Attendee

```shell
curl -X PATCH 
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/attendees/12" 
  -d '{
    "data": {
      "id": 12,
      "type": "attendees",
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
    "type": "attendees",
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
  "https://api.weteachme.com/v1/attendees/12", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one attendee by id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/attendees/12`

## DELETE Attendee

```shell
curl -X DELETE 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/attendees/12" 
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.delete(
  "https://api.weteachme.com/v1/attendees/12", 
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => 'meowmeowmeow'"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one attendee by id.

### HTTP Request

`DELETE https://api.weteachme.com/v1/attendees/12`
