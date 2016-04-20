# Dates

## READ All Datees

```shell
curl 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/dates"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/dates?page[number]=1&page[size]=20&fields[dates]=name,startdatetime", 
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
      "type":"dates",
      "links":{"self":"/v1/dates/224476"},
      "attributes": {
        "name": "How to Make Coffee Beans",
        "location": "41 Steward St, Richmond, VIC 3121",
        "thumbnail": "https://some-dns-hosted.com/url/thumbnail.jpg"
      },
      "relationships": {
        "attendees": {
          "links": {
            "related": "/v1/attendees?filter[class-list-id]=224476"
          }
        }
      }
    }
  ]
}
```

This endpoint retrieves all dates.

### HTTP Request

`GET https://api.weteachme.com/v1/dates`

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
min-date      | string     |  dd/mm/yyyy
max-date      | string     |  dd/mm/yyyy
min-amount    | number     |  
max-amount    | number     |  
class-id      | number     |  Class Id

### Sorting Fields

Parameter  | Example
---------- | -----------
name  | name | -name


## READ Date

```shell
curl 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/dates/1231212"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/dates/1231212", 
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
    "type":"dates",
    "links":{"self":"/v1/dates/224476"},
    "attributes": {
      "start-datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "end-datetime": "Thu Feb 04 2016 22:30:00 GMT+1100 (AEDT)",
      "class-id": 1231,
      "capacity": 50,
      "sold": 30
    },
    "relationships": {
      "attendees": {
        "links": {
          "related": "/v1/attendees?filter[class-list-id]=224476"
        }
      }
    }
  }
}
```

This endpoint retrieves one date by id.

### HTTP Request

`GET https://api.weteachme.com/v1/date/1212`


## CREATE Date

```shell
curl -X POST
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json"
  "https://api.weteachme.com/v1/dates" 
  -d '{
    "data": {
      "type": "dates",
      "attributes": {
        "start-datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "end-datetime": "Thu Feb 04 2016 22:30:00 GMT+1100 (AEDT)",
        "class-id": 1231,
        "capacity": 50,
        "sold": 30
      }
    }
  }'
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

payload = {
  "data": {
    "type": "dates",
    "attributes": {
      "start-datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "end-datetime": "Thu Feb 04 2016 22:30:00 GMT+1100 (AEDT)",
      "class-id": 1231,
      "capacity": 50,
      "sold": 30
    }
  }
}
HTTParty.post(
  "https://api.weteachme.com/v1/dates", 
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
    "type":"dates",
    "links":{
      "self":"/v1/dates/224476"
    },
    "attributes": {
      "start-datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "end-datetime": "Thu Feb 04 2016 22:30:00 GMT+1100 (AEDT)",
      "class-id": 1231,
      "capacity": 50,
      "sold": 30
    }
  }
}
```

This endpoint creates one date.

### HTTP Request

`POST https://api.weteachme.com/v1/dates`


## UPDATE Date

```shell
curl -X PATCH 
  -H "Content-Type: application/vnd.api+json" 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/dates/12" 
  -d '{
    "data": {
      "id": 12,
      "type": "dates",
      "attributes": {
        "start-datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "end-datetime": "Thu Feb 04 2016 22:30:00 GMT+1100 (AEDT)",
        "class-id": 1231,
        "capacity": 50,
        "sold": 30
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
    "type": "dates",
    "attributes": {
      "start-datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
      "end-datetime": "Thu Feb 04 2016 22:30:00 GMT+1100 (AEDT)",
      "class-id": 1231,
      "capacity": 50,
      "sold": 30
    }
  }
}
HTTParty.patch(
  "https://api.weteachme.com/v1/dates/12", 
  payload,
  headers: {
    "Content-Type" => 'application/vnd.api+json', 
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => meowmeowmeow"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one date by id.

### HTTP Request

`PATCH https://api.weteachme.com/v1/dates/12`

## DELETE Date

```shell
curl -X DELETE 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/dates/12" 
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.delete(
  "https://api.weteachme.com/v1/dates/12", 
  headers: {
    "Accept" => 'application/vnd.api+json', 
    "API-KEY" => 'meowmeowmeow'"
  }
);

```

> The above command returns HTTP/1.1 204 No Content


This endpoint updates one date by id.

### HTTP Request

`DELETE https://api.weteachme.com/v1/dates/12`
