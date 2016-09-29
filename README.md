# GEO PACK API

This is a REST-style API that uses JSON for serialization

# Where do I start?

Want to get started with API integration? Here's a quick check list:

1. Register as an ecommerce in [Geo Pack](https://geopack.me/ecommerce/sign_up).
2. Once inside your ecommerce's admin panel, go to the "Apps" section and create your app.
3. Read up on how to authenticate your app with us.
4. Read the API docs to understand what you can do with your app.

# Making a request

All URLs start with `https://geopack.me/ecommerce/v1/(ecommerce_id)`. SSL only. The path is prefixed with the store id and the API version. If we change the API in backward-incompatible ways, we'll bump the version marker and maintain stable support for the old URLs.

So if you want to access the ecommerce with id 21357 via the API, the url will be `https://geopack.me/ecommerce/v1/(ecommerce_id)`.

To make a request for all the ecommerce's roadmap you would do the following in curl:

```shell

curl -H 'Authentication: bearer ACCESS_TOKEN ' \
  -H 'User-Agent: (ecommerce_name)' \
  https://geopack.me/ecommerce/v1/(ecommerce_id)/roadmap

```

where ACCESS_TOKEN is the ecommerce's access token for your app (see Authentication).

To create something, you have to include the Content-Type header and the JSON data:

```shell

curl -H 'Authentication: bearer ACCESS_TOKEN ' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: (ecommerce_name)' \
  -d '{ }' \
  https://geopack.me/ecommerce/v1/(ecommerce_id)/roadmap

```

# Authentication

```shell


```

# [Api Resources] (resources)

[Roadmap](resources/roadmap.md)

[Stage](resources/stage.md)
