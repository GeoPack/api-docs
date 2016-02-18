# GEO PACK API

This is a REST-style API that uses JSON for serialization

# Where do I start?

Want to get started with API integration? Here's a quick check list:

1. Register as a ecommerce in Geo Pack.
2. Once inside your ecommerce's admin panel, go to the "Apps" section and create your app.
3. Read up on how to authenticate your app with us.
4. Read the API docs to understand what you can do with your app.

# Making a request

All URLs start with `https://geopack.me/ecommerce/v1/(ecommerce_id)`. SSL only. The path is prefixed with the store id and the API version. If we change the API in backward-incompatible ways, we'll bump the version marker and maintain stable support for the old URLs.

So if you want to access the ecommerce with id 21357 via the API the url will be `https://geopack.me/ecommerce/v1/(ecommerce_id)`.

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
  -d '{ "name": "My new roadmap" }' \
  https://geopack.me/ecommerce/v1/(ecommerce_id)/roadmap

```

# Authentication
```shell


```


# Set roadmap

```shell
{
    "start": {
        "address": {
            "street": "Calle 8",
            "number": "12300",
            "locality": "San Carlos de Bariloche, R\u00edo Negro",
            "reference": null,
            "lat": "",
            "lng": ""
        },
        "contact": {
            "name": "Diego",
            "lastname": "D'Alto",
            "gender": "male",
            "birthday": "1983\/09\/05",
            "mail": "dm.dalto@hotmail.com",
            "mobile": "5491132038575"
        },
        "stage": -4
    },
    "end": {
        "address": {
            "street": "Calle 2",
            "number": "12100",
            "locality": "Villa Nahuel Malal, San Carlos de Bariloche, R\u00edo Negro",
            "reference": null,
            "lat": "",
            "lng": ""
        },
        "contact": {
            "name": "Cecilia",
            "lastname": "Gioffr\u00e9",
            "gender": "female",
            "birthday": "1985\/03\/29",
            "mail": "ceciliagioffre@gmail.com",
            "mobile": "5491140482165"
        },
        "stage": -4
    },
    "waytpoint": [ # It's optional
        {
            "address": {
                "street": "Calle 4",
                "number": "11600",
                "locality": "Villa Nahuel Malal, San Carlos de Bariloche, R\u00edo Negro",
                "reference": null,
                "lat": "",
                "lng": ""
            },
            "contact": {
                "name": "Cecilia",
                "lastname": "Gioffr\u00e9",
                "gender": "female",
                "birthday": "1985\/03\/29",
                "mail": "ceciliagioffre@gmail.com",
                "mobile": "5491140482165"
            },
            "stage": -4
        }
    ]
}
```



