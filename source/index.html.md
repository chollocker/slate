---

title: 3Victors API Documents - Real Time Prices Service

language_tabs:
   - shell
   - javascript

toc_footers:
   - <a href='#'>Contact 3Victors for more information</a>
   - <a href='https://www.3victors.com/'>Documentation Powered by Slate</a>

includes:
   - errors

search: true

---

# Introduction - Real Time Prices Service APIs

3Victors is a Travel Big Data company ingesting daily over 500 million worldwide travel searches and 90 billion itineraries in real-time from the world’s largest reservation systems.
Providing data analytic solutions specific to your needs with insights into market trends, pricing, and lowest fares.
Whether you need real-time access, hourly, daily, or a weekly summary, we have a solution to meet your needs.

**Version:** 1.0.0

[Find out more about 3Victors](https://www.3victors.com/)

# Authentication

|Content-Type|application/json;charset=UTF-8|
|---|---|

|x-api-key|Email <support@3victors.com> to request an API Key|
|---|---|

# getCheapestPriceForTrip
## ***POST***

**Summary:** Returns the cheapest price for a market with alternatives.

**Description:** Returns the cheapest price, carrier, & stops, and carrier / stop alternatives for an origin, destination, depart date, and return date.

### HTTP Request
`***POST*** RealTimePricesService/getCheapestPriceForTrip`

> Sample request

```shell
curl -X POST \
  'https://prices.3victors.com/RealTimePricesService/getCheapestPriceForTrip?=' \
  -H 'Content-Type: application/json;charset=UTF-8' \
  -H 'Postman-Token: 3a664748-c16a-4f8e-85cb-539c030feeee' \
  -H 'cache-control: no-cache' \
  -H 'x-api-key: <x-api-key-value>'\
  -d '{
  "origin" : "OME",
  "destination" : "ANC",
  "departDate" : "20190319",
  "returnDate" : "20190402"
}'
```

```javascript
{
  "origin" : "OME",
  "destination" : "ANC",
  "departDate" : "20190319",
  "returnDate" : "20190402"
}
```

**Request Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| origin | body | Requested ATPCO origin airport code | Yes | String |
| destination | body | Requested ATPCO destination airport code | Yes | String |
| departDate | body | Departure date | Yes | Integer YYYYMMDD |
| returnDate | body | Return date | Yes | Integer YYYYMMDD |

> Sample response

```shell
{
    "cheapest": {
        "originAirportCode": "OME",
        "destinationAirportCode": "ANC",
        "carrierCode": "AS",
        "stops": 1,
        "price": 338.2,
        "departDate": 20190319,
        "returnDate": 20190402
    },
    "details": [
        {
            "originAirportCode": "OME",
            "destinationAirportCode": "ANC",
            "carrierCode": "AS",
            "stops": 0,
            "price": 378.2,
            "departDate": 20190319,
            "returnDate": 20190402
        }
    ],
    "error": null
}
```

```javascript
{
    "cheapest": {
        "originAirportCode": "OME",
        "destinationAirportCode": "ANC",
        "carrierCode": "AS",
        "stops": 1,
        "price": 338.2,
        "departDate": 20190319,
        "returnDate": 20190402
    },
    "details": [
        {
            "originAirportCode": "OME",
            "destinationAirportCode": "ANC",
            "carrierCode": "AS",
            "stops": 0,
            "price": 378.2,
            "departDate": 20190319,
            "returnDate": 20190402
        }
    ],
    "error": null
}
```

**Responses**

*cheapest (the cheapest overall carrier/number of stops for the market)*

| Params | Values |
| ---- | ----------- |
| originAirportCode | ATPCO origin airport code |
| destinationAirportCode | ATPCO destination airport code |
| carrierCode | IATA validating carrier code |
| stops | Maximum number of stops |
| price | Itinerary price |
| departDate | Departure date. Format: YYYYMMDD |
| returnDate | Return date. Format: YYYYMMDD. 0 for oneway trip |

*details (repeats for each carrier/number of stops for the market)*

| Params | Values |
| ---- | ----------- |
| originAirportCode | ATPCO origin airport code |
| destinationAirportCode | ATPCO destination airport code |
| carrierCode | IATA validating carrier code |
| stops | Maximum number of stops |
| price | Itinerary price |
| departDate | Departure date. Format: YYYYMMDD |
| returnDate | Return date. Format: YYYYMMDD. 0 for oneway trip |

# getCheapestPricePerDepartDate
## ***POST***

**Summary:** Returns the cheapest price for each departure date.

**Description:** Returns the cheapest price for each departure date in a specified range for an origin / destination.

### HTTP Request
`***POST*** RealTimePricesService/getCheapestPricePerDepartDate`

> Sample request

```shell
curl -X POST \
  https://prices.3victors.com/RealTimePricesService/getCheapestPricePerDepartDate \
  -H 'Content-Type: application/json;charset=UTF-8' \
  -H 'Postman-Token: f5a092b8-f7d3-4090-9590-b0cce40fb313' \
  -H 'cache-control: no-cache' \
  -H 'x-api-key: <x-api-key-value>\
  -d '{
  "origin" : "CUN",
  "destination" : "EWR",
  "roundtrip" : "true",
  "departDateStart" : "20190926",
  "departDateEnd" : "20190928"
}'
```

```javascript
{
  "origin" : "CUN",
  "destination" : "EWR",
  "roundtrip" : "true",
  "departDateStart" : "20190926",
  "departDateEnd" : "20190928"
}
```

**Request Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| origin | body | Requested ATPCO origin airport code | Yes | String |
| destination | body | Requested ATPCO destination airport code | Yes | String |
| roundtrip | body | Send “true” for roundtrip and “false” for oneway trips. Defaults to true if missing. | No | Boolean |
| departDateStart | body | Start departure date. Defaults to today if missing. | No | Integer YYYYMMDD |
| departDateEnd | body | End departure date | No | Integer YYYYMMDD |

> Sample response

```shell
{
"20190926": [
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!T",
        "stops": 1,
        "price": 234.91,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!T",
        "stops": 2,
        "price": 273.11,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "NK",
        "stops": 1,
        "price": 277.04,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 2,
        "price": 342.93,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AA",
        "stops": 1,
        "price": 372.35,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "DL",
        "stops": 1,
        "price": 422.39,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 1,
        "price": 426.42,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 1,
        "price": 428.72,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 0,
        "price": 516,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AC",
        "stops": 1,
        "price": 553.97,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "DL",
        "stops": 2,
        "price": 568.65,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!!",
        "stops": 1,
        "price": 574.51,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AA",
        "stops": 2,
        "price": 761.31,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!A",
        "stops": 1,
        "price": 1121.74,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 2,
        "price": 1171.23,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!!",
        "stops": 0,
        "price": 1194.1,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!!",
        "stops": 2,
        "price": 1928.63,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!A",
        "stops": 2,
        "price": 2344.91,
        "departDate": 20190926
    }
],
"20190927": [
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 1,
        "price": 379.21,
        "departDate": 20190927
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 2,
        "price": 605.91,
        "departDate": 20190927
    }
],
"20190928": [
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 1,
        "price": 374.71,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 1,
        "price": 481.19,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 2,
        "price": 532.01,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 0,
        "price": 609.15,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AC",
        "stops": 1,
        "price": 626.07,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!!",
        "stops": 1,
        "price": 723.7,
        "departDate": 20190928
    }
]
}
```

```javascript
{
"20190926": [
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!T",
        "stops": 1,
        "price": 234.91,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!T",
        "stops": 2,
        "price": 273.11,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "NK",
        "stops": 1,
        "price": 277.04,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 2,
        "price": 342.93,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AA",
        "stops": 1,
        "price": 372.35,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "DL",
        "stops": 1,
        "price": 422.39,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 1,
        "price": 426.42,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 1,
        "price": 428.72,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 0,
        "price": 516,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AC",
        "stops": 1,
        "price": 553.97,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "DL",
        "stops": 2,
        "price": 568.65,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!!",
        "stops": 1,
        "price": 574.51,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AA",
        "stops": 2,
        "price": 761.31,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!A",
        "stops": 1,
        "price": 1121.74,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 2,
        "price": 1171.23,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!!",
        "stops": 0,
        "price": 1194.1,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!!",
        "stops": 2,
        "price": 1928.63,
        "departDate": 20190926
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!A",
        "stops": 2,
        "price": 2344.91,
        "departDate": 20190926
    }
],
"20190927": [
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 1,
        "price": 379.21,
        "departDate": 20190927
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 2,
        "price": 605.91,
        "departDate": 20190927
    }
],
"20190928": [
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 1,
        "price": 374.71,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 1,
        "price": 481.19,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AM",
        "stops": 2,
        "price": 532.01,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "UA",
        "stops": 0,
        "price": 609.15,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "AC",
        "stops": 1,
        "price": 626.07,
        "departDate": 20190928
    },
    {
        "originAirportCode": "CUN",
        "destinationAirportCode": "EWR",
        "carrierCode": "!!",
        "stops": 1,
        "price": 723.7,
        "departDate": 20190928
    }
]
}
```

**Responses**

*departDate (repeats for each departure date)*

| Params | Values |
| ---- | ----------- |
| originAirportCode | ATPCO origin airport code |
| destinationAirportCode | ATPCO destination airport code |
| carrierCode | IATA validating carrier code |
| stops | Maximum number of stops |
| price | Itinerary price |
| departDate | Departure date. Format: YYYYMMDD |

# getCheapestPricePerReturnDate
## ***POST***

**Summary:** Returns the cheapest price for each return date.

**Description:** Returns the cheapest price for a given origin, destination, and carrier for each return date between a specified departure date and ending return date.

### HTTP Request
`***POST*** RealTimePricesService/getCheapestPricePerReturnDate`

> Sample request

```shell
curl -X POST \
  https://prices.3victors.com/RealTimePricesService/getCheapestPricePerReturnDate \
  -H 'Content-Type: application/json;charset=UTF-8' \
  -H 'Postman-Token: 852c5a71-e974-40f3-8a33-8b638bcfa7c8' \
  -H 'cache-control: no-cache' \
  -H 'x-api-key: <x-api-key-value>\
  -d '{
  "origin" : "DFW",
  "destination" : "ORD",
  "carrierCode" : "AA",
  "departDate" : "20190320",
  "returnDateEnd" : "20190330"
}'
```

```javascript
{
  "origin" : "DFW",
  "destination" : "ORD",
  "carrierCode" : "AA",
  "departDate" : "20190320",
  "returnDateEnd" : "20190330"
}
```

**Request Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| origin | body | Requested ATPCO origin airport code | Yes | String |
| destination | body | Requested ATPCO destination airport code | Yes | String |
| carrierCode | body | Validating IATA carrier code to return | Yes | String |
| departDate | body | Departure date. Departure date is also starting return date. | Yes | Integer YYYYMMDD |
| returnDateEnd | body | End return date | Yes | Integer YYYYMMDD |

> Sample response

```shell
{
"20190320": [
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 0,
        "price": 787.78,
        "departDate": 20190320,
        "returnDate": 20190320
    }
],
"20190322": [
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 1,
        "price": 795.3,
        "departDate": 20190320,
        "returnDate": 20190322
    }
],
"20190323": [
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 0,
        "price": 674.6,
        "departDate": 20190320,
        "returnDate": 20190323
    },
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 1,
        "price": 683.3,
        "departDate": 20190320,
        "returnDate": 20190323
    }
],
"20190326": [
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 1,
        "price": 525,
        "departDate": 20190320,
        "returnDate": 20190326
    },
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 2,
        "price": 529.2,
        "departDate": 20190320,
        "returnDate": 20190326
    },
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 0,
        "price": 674.6,
        "departDate": 20190320,
        "returnDate": 20190326
    }
]
}
```

```javascript
{
"20190320": [
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 0,
        "price": 787.78,
        "departDate": 20190320,
        "returnDate": 20190320
    }
],
"20190322": [
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 1,
        "price": 795.3,
        "departDate": 20190320,
        "returnDate": 20190322
    }
],
"20190323": [
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 0,
        "price": 674.6,
        "departDate": 20190320,
        "returnDate": 20190323
    },
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 1,
        "price": 683.3,
        "departDate": 20190320,
        "returnDate": 20190323
    }
],
"20190326": [
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 1,
        "price": 525,
        "departDate": 20190320,
        "returnDate": 20190326
    },
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 2,
        "price": 529.2,
        "departDate": 20190320,
        "returnDate": 20190326
    },
    {
        "originAirportCode": "DFW",
        "destinationAirportCode": "ORD",
        "carrierCode": "AA",
        "stops": 0,
        "price": 674.6,
        "departDate": 20190320,
        "returnDate": 20190326
    }
]
}
```

**Responses**

*returnDate (repeats for each return date)*

| Params | Values |
| ---- | ----------- |
| originAirportCode | ATPCO origin airport code |
| destinationAirportCode | ATPCO destination airport code |
| carrierCode | IATA validating carrier code |
| stops | Maximum number of stops |
| price | Itinerary price |
| departDate | Departure date. Format: YYYYMMDD |
| returnDate | Return date. Format: YYYYMMDD |

# getMeOutOfTown
## ***POST***

**Summary:** Returns weekend deals from an origin.

**Description:** Returns weekend deals from an origin. Weekend departures are Thursday, Friday, and Saturday. 

### HTTP Request
`***POST*** RealTimePricesService/getMeOutOfTown`

> Sample request

```shell
curl -X POST \
   https://prices.3victors.com/RealTimePricesService/getMeOutOfTown \
   -H 'Content-Type: application/json;charset=UTF-8' \
   -H 'Postman-Token: 639d2ec2-1771-4c45-a7f5-54f8ae8c1dc7' \
   -H 'cache-control: no-cache' \
   -H 'x-api-key: <x-api-key-value>\
   -d '{
  "origin" : "ABI",
  "destinations" : ["LAX","ONT","SNA","SAT","OAK","DEN","SJC","BUR"],
  "weekend" : "2"
}'
```

```javascript
{
  "origin" : "ABI",
  "destinations" : ["LAX","ONT","SNA","SAT","OAK","DEN","SJC","BUR"],
  "weekend" : "2"
}
```

**Request Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| origin | body | Requested ATPCO origin airport code | Yes | String |
| destinations | body | List of ATPCO destination airport code(s) to examine. Defaults to all if missing. | No | String array enclosed in [] |
| weekend | body | Number of weekends out for deals. 0 returns deals for upcoming weekend, 1 for the following weekend, etc. | Yes | Integer |

> Sample response

```shell
{
"LAX": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "LAX",
        "carrierCode": "AA",
        "stops": 1,
        "price": 429.6,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "LAX",
        "carrierCode": "AA",
        "stops": 2,
        "price": 528.8,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "LAX",
        "carrierCode": "AS",
        "stops": 2,
        "price": 2448.01,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "LAX",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2721.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
],
"ONT": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "ONT",
        "carrierCode": "AA",
        "stops": 1,
        "price": 499.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "ONT",
        "carrierCode": "AA",
        "stops": 2,
        "price": 576.8,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "ONT",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2654.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
],
"SNA": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SNA",
        "carrierCode": "AA",
        "stops": 1,
        "price": 459.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SNA",
        "carrierCode": "AA",
        "stops": 2,
        "price": 541.8,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SNA",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2940.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
],
"SAT": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SAT",
        "carrierCode": "AA",
        "stops": 1,
        "price": 405.6,
        "departDate": 20190405,
        "returnDate": 20190407
    }
],
"OAK": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "OAK",
        "carrierCode": "AA",
        "stops": 1,
        "price": 429.6,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "OAK",
        "carrierCode": "AA",
        "stops": 2,
        "price": 531.8,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "OAK",
        "carrierCode": "AA",
        "stops": 3,
        "price": 625.99,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "OAK",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2341.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
],
"DEN": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "AA",
        "stops": 1,
        "price": 395.6,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "AA",
        "stops": 1,
        "price": 395.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "AA",
        "stops": 2,
        "price": 613.8,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "AS",
        "stops": 2,
        "price": 2545,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "!!",
        "stops": 2,
        "price": 3252,
        "departDate": 20190405,
        "returnDate": 20190407
    }
],
"SJC": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AA",
        "stops": 1,
        "price": 429.6,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AA",
        "stops": 1,
        "price": 429.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AA",
        "stops": 2,
        "price": 433.8,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AA",
        "stops": 2,
        "price": 433.8,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AS",
        "stops": 2,
        "price": 1058.01,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AS",
        "stops": 3,
        "price": 1501.2,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "!!",
        "stops": 2,
        "price": 1664.8,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "!!",
        "stops": 1,
        "price": 1739.62,
        "departDate": 20190404,
        "returnDate": 20190407
    }
],
"BUR": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "BUR",
        "carrierCode": "AA",
        "stops": 1,
        "price": 459.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "BUR",
        "carrierCode": "AA",
        "stops": 2,
        "price": 541.8,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "BUR",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2762.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
]
}
```

```javascript
{
"LAX": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "LAX",
        "carrierCode": "AA",
        "stops": 1,
        "price": 429.6,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "LAX",
        "carrierCode": "AA",
        "stops": 2,
        "price": 528.8,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "LAX",
        "carrierCode": "AS",
        "stops": 2,
        "price": 2448.01,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "LAX",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2721.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
],
"ONT": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "ONT",
        "carrierCode": "AA",
        "stops": 1,
        "price": 499.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "ONT",
        "carrierCode": "AA",
        "stops": 2,
        "price": 576.8,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "ONT",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2654.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
],
"SNA": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SNA",
        "carrierCode": "AA",
        "stops": 1,
        "price": 459.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SNA",
        "carrierCode": "AA",
        "stops": 2,
        "price": 541.8,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SNA",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2940.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
],
"SAT": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SAT",
        "carrierCode": "AA",
        "stops": 1,
        "price": 405.6,
        "departDate": 20190405,
        "returnDate": 20190407
    }
],
"OAK": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "OAK",
        "carrierCode": "AA",
        "stops": 1,
        "price": 429.6,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "OAK",
        "carrierCode": "AA",
        "stops": 2,
        "price": 531.8,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "OAK",
        "carrierCode": "AA",
        "stops": 3,
        "price": 625.99,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "OAK",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2341.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
],
"DEN": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "AA",
        "stops": 1,
        "price": 395.6,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "AA",
        "stops": 1,
        "price": 395.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "AA",
        "stops": 2,
        "price": 613.8,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "AS",
        "stops": 2,
        "price": 2545,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "DEN",
        "carrierCode": "!!",
        "stops": 2,
        "price": 3252,
        "departDate": 20190405,
        "returnDate": 20190407
    }
],
"SJC": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AA",
        "stops": 1,
        "price": 429.6,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AA",
        "stops": 1,
        "price": 429.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AA",
        "stops": 2,
        "price": 433.8,
        "departDate": 20190405,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AA",
        "stops": 2,
        "price": 433.8,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AS",
        "stops": 2,
        "price": 1058.01,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "AS",
        "stops": 3,
        "price": 1501.2,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "!!",
        "stops": 2,
        "price": 1664.8,
        "departDate": 20190404,
        "returnDate": 20190407
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "SJC",
        "carrierCode": "!!",
        "stops": 1,
        "price": 1739.62,
        "departDate": 20190404,
        "returnDate": 20190407
    }
],
"BUR": [
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "BUR",
        "carrierCode": "AA",
        "stops": 1,
        "price": 459.6,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "BUR",
        "carrierCode": "AA",
        "stops": 2,
        "price": 541.8,
        "departDate": 20190405,
        "returnDate": 20190408
    },
    {
        "originAirportCode": "ABI",
        "destinationAirportCode": "BUR",
        "carrierCode": "!!",
        "stops": 2,
        "price": 2762.8,
        "departDate": 20190405,
        "returnDate": 20190408
    }
]
}
```

**Responses**

*destination (repeats for each destination)*

| Params | Values |
| ---- | ----------- |
| originAirportCode | ATPCO origin airport code |
| destinationAirportCode | ATPCO destination airport code |
| carrierCode | IATA validating carrier code |
| stops | Maximum number of stops |
| price | Itinerary price |
| departDate | Departure date. Format: YYYYMMDD |
| returnDate | Return date. Format: YYYYMMDD. 0 for oneway trip |

## ***DELETE***

**Summary:** Delete user

**Description:** This can only be done by the logged in user.

### HTTP Request
`***DELETE*** /user/{username}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be deleted | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid username supplied |
| 404 | User not found |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
