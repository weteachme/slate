# Errors

The WeTeachMe API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The kitten requested is hidden for administrators only
404 | Not Found -- The specified kitten could not be found
405 | Method Not Allowed -- You tried to access a kitten with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The kitten requested has been removed from our servers
418 | I'm a teapot
429 | Too Many Requests -- You're requesting too many kittens! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.


> ### Example Error Response
```shell
# Multi errors with same status

HTTP/1.1 422 Unprocessable Entity
Content-Type: application/vnd.api+json
```

```json
{
  "errors": [
    {
      "status": "422",
      "source": { "pointer": "/data/attributes/first-name" },
      "title": "Invalid Attribute",
      "detail": "First name must contain at least three characters."
    },
    {
      "status": "422",
      "source": { "pointer": "/data/attributes/first-name" },
      "title": "Invalid Attribute",
      "detail": "First name must contain at least three characters."
    }
  ]
}
```

```shell
# Multi errors with different status

HTTP/1.1 400 Unprocessable Entity
Content-Type: application/vnd.api+json
```
```json
{
  "errors": [
    {
      "status": "422",
      "source": { "pointer": "/data/attributes/first-name" },
      "title": "Invalid Attribute",
      "detail": "First name must contain at least three characters."
    },
    {
      "status": "500",
      "source": { "pointer": "/data/attributes/reputation" },
      "title": "The backend responded with an error",
      "detail": "Reputation service not responding after three requests."
    }

  ]
}
```
