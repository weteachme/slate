---
title: API Reference

language_tabs:
  - shell
  - ruby

toc_footers:
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - attendees
  - classes
  - dates
  - orders
  - transactions
  - merchandises
  - errors

search: true
---

# Introduction

Welcome to the WeTeachMe API! You can use our API to access WeTeachMe API endpoints.

WeTeachMe API follows [JSON API](http://jsonapi.org/format/) v1.0, which requires use of the JSON API media type (application/vnd.api+json) for exchanging data.

We have language bindings in Shell and Ruby! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This API documentation page was created with [Slate](http://github.com/tripit/slate).

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```ruby
require 'weteachme'

api = WeTeachMe::APIClient.authorize!('meowmeowmeow')
```

> Make sure to replace `meowmeowmeow` with your API key.

WeTeachMe uses API keys to allow access to the API. You can get the API key under your [account settings](https://dashboard.weteachme.com/account/settings).

API key is expected to be included in all API requests to the server in a header that looks like the following:

`API_KEY: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your API key.
</aside>
