# Set roadmap

This creates a new roadmap in the system that will show up to a nearest geopacker to the pickup point.

### POST /roadmap

##### Open json
```shell

{

```

##### Start
`Pick up address`
```shell

  "start": {
      "address": {
          "street": "Carlos Francisco Melo",
          "number": "3410",
          "locality": "Villa Martelli, Buenos Aires",
          "reference": null, # or "5 c"
          "lat": "-34.5691192", # or empty
          "lng": "-58.4739864"  # or empty
      },
      "contact": {
          "name": "******",
          "lastname": "*******",
          "gender": "female", # or male
          "birthday": "****\/**\/**",
          "mail": "*********@*****.***",
          "mobile": "54911********"
      }
  },
  
```
##### Waytpoint is optional
`Stopover`
```shell

  "waytpoint": [
    {
        "address": {
            "street": "Av. Corrientes",
            "number": "1500",
            "locality": "C1042AAN CABA",
            "reference": "3 B", # or null
            "lat": "-34.6041021", # or empty
            "lng": "-58.3901012"  # or empty
        },
        "contact": {
            "name": "******",
            "lastname": "*******",
            "gender": "female", # or male
            "birthday": "****\/**\/**",
            "mail": "********@****.**",
            "mobile": "54911********"
        }
    }
  ],

```

##### End
`Delivery address`
```shell

  "end": {
      "address": {
          "street": "Av Cabildo 2901",
          "number": "2901",
          "locality": "C1429AAA CABA",
          "reference": "4 A", # or null
          "lat": "", # or -34.555172
          "lng": ""  # or -58.4646787
      },
      "contact": {
          "name": "******",
          "lastname": "*******",
          "gender": "female", # or male
          "birthday": "****\/**\/**",
          "mail": "*********@*****.***",
          "mobile": "54911********"
      }
  },
  "stage": "unauthorized" # or "pending"


```

##### Close json
```shell

}

```


`HTTP/1.1 201 Created`

```shell

{
    "id": "***",
    "delivery": [
        {
            "mail": "******",
            "qr": "***" #url
        },
        {
            "mail": "******",
            "qr": "***" #url
        }
    ],
    "price": **
}

```

### GET /roadmap/:id

| Parameter | Explanation |
| --- | --- |
| id | Show roadmap |

`HTTP/1.1 200 OK`

```shell

{
    "start": {
        "address": {
            "street": "Av. Corrientes",
            "number": "1500",
            "locality": "C1042AAN CABA",
            "reference": "3 B",
            "lat": "-34.6041021",
            "lng": "-58.3901012"
        },
        "contact": {
            "name": "******",
            "lastname": "*******",
            "gender": "female",
            "birthday": "****\/**\/**",
            "mail": "********@****.**",
            "mobile": "54911********"
        },
        "stage": "******"
    },
    "end": {
        "address": {
            "street": "Av Cabildo 2901",
            "number": "2901",
            "locality": "C1429AAA CABA",
            "reference": "4 A",
            "lat": "-34.555172",
            "lng": "-58.4646787"
        },
        "contact": {
            "name": "******",
            "lastname": "*******",
            "gender": "female",
            "birthday": "****\/**\/**",
            "mail": "*********@*****.***",
            "mobile": "54911********"
        },
        "stage": "******"
    },
    "datetime": "2016-02-23 19:17:58",
    "price": 75,
    "distance": 2,
    "geopacker": {
        "name": null,
        "lastname": null,
        "gender": null,
        "birthday": null,
        "mail": null,
        "mobile": null
    },
    "waytpoint": [
        {
          {
            "address": {
                "street": "Av. Corrientes",
                "number": "1500",
                "locality": "C1042AAN CABA",
                "reference": "3 B",
                "lat": "-34.6041021",
                "lng": "-58.3901012"
            },
            "contact": {
                "name": "******",
                "lastname": "*******",
                "gender": "female",
                "birthday": "****\/**\/**",
                "mail": "********@****.**",
                "mobile": "54911********"
            },
            "stage": "******"
        }
    ]
}

```

### PUT /roadmap/:id/stage/:stage

| Stage |
|---|
| cancel |
| pickup |
| receive |
| unauthorized |


Modify an existing stage roadmap

`HTTP/1.1 201 Created`

```shell

{
    "status": "OK",
    "stage": "cancel"
}

```

