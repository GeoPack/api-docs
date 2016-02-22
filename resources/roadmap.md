# Set roadmap

This creates a new roadmap in the system that will show up to a nearest geopacker to the pickup point.

Name | data
--- | ---
start 
waypoint 
end | address, contact, stage


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
          "mail": "********6@*****.***",
          "mobile": "54911********"
      },
      "stage": -4
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
        },
        "stage": -4
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
          "mail": "********6@*****.***",
          "mobile": "54911********"
      },
      "stage": -4
  } 


```

##### Close json
```shell

}

```
