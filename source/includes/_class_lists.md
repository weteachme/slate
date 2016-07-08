# Class List

## READ All Active Class Dates

```shell
curl 
  -H "Accept: application/vnd.api+json" 
  "https://api.weteachme.com/v1/class-lists?page[number]=1&page[size]=20"
  -H "API-KEY: meowmeowmeow"
```

```ruby
require 'httparty'

HTTParty.get(
  "https://api.weteachme.com/v1/class-lists?page[number]=1&page[size]=20", 
  headers: {
    "Accept" => 'application/vnd.api+json', 
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
      "type":"transactions",
      "links":{"self":"/v1/transactions/224476"},
      "attributes": {
        "name": "How to make coffee",
        "datetime": "Thu Feb 04 2016 20:30:00 GMT+1100 (AEDT)",
        "address": "Level 3, 41-43 Stewart St, Richmond",
        "sold": 10,
        "capacity": 20,
        "class_number": 3,
        "session_name": "Week"
      }
    }
  ]
}
```

This endpoint retrieves all class dates.

### HTTP Request

`GET https://api.weteachme.com/v1/class-lists`

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
name          | string     |  Class Name
address       | string     |  Class Location
min-date      | string     |  dd/mm/yyyy
max-date      | string     |  dd/mm/yyyy
tag-id        | number     |  
