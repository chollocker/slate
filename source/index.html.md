---

title: Real Time Prices Service APIs

language_tabs:
   - shell
   - javascript

toc_footers:
   - <a href='https://www.3victors.com/'>Contact 3Victors for more information</a>

includes:
   - errors

search: true

---

# 3Victors

3Victors is a Travel Big Data company ingesting daily over 500 million worldwide travel searches and 90 billion itineraries in real-time from the world’s largest reservation systems.
Providing data analytic solutions specific to your needs with insights into market trends, pricing, and lowest fares.
Whether you need real-time access, hourly, daily, or a weekly summary, we have a solution to meet your needs.

Documentation powered by Slate

**Version:** 1.0.0

[Find out more about 3Victors](https://www.3victors.com/)

# Real Time Prices Service APIs

## Authentication

| Key | Value |
| ---- | ---------- |
| Content-Type | application/json;charset=UTF-8 |
| x-api-key | Email <support@3victors.com> to request an API Key| |

## getCheapestPriceForTrip
### ***POST***

**Summary:** Returns the cheapest price for a market with alternatives.

**Description:** Returns the cheapest price, carrier, & stops, and carrier / stop alternatives for an origin, destination, depart date, and return date.

### HTTP Request
`***POST*** RealTimePricesService/getCheapestPriceForTrip`

> Sample request

```shell
curl -X POST \
  https://api.3victorseap.com/RealTimePricesService/getCheapestPriceForTrip \
  -H 'Accept: */*' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Length: 101' \
  -H 'Content-Type: application/json;charset=UTF-8' \
  -H 'Cookie: AWSELB=2103831F10BD9B792611B4BD5039EF955C04081CCDC882B5F1C0105CC0CD65CF87B7D25C94CD4D335F69C984E773DED9B6F97D049A2CA55BB1A83BEB15D6FA011B50552E31' \
  -H 'Host: api.3victorseap.com' \
  -H 'Postman-Token: <TOKEN>' \
  -H 'User-Agent: PostmanRuntime/7.16.3' \
  -H 'cache-control: no-cache' \
  -H 'x-api-key: jCtEGyn3x44akvfYHOCw31NLVSHZoy3g3WYECkmm' \
  -d '{
  "origin" : "ATL",
  "destination" : "MIA",
  "departDate" : 20200301,
  "returnDate" : 20200303
}'
```

```javascript
{
  "origin" : "LAX",
  "destination" : "SFO",
  "departDate" : 20200301,
  "returnDate" : 0
}
```

**Request Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| origin | body | Requested IATA origin airport code | Yes | String |
| destination | body | Requested IATA destination airport code | Yes | String |
| departDate | body | Departure date | Yes | Integer YYYYMMDD |
| returnDate | body | Return date | Yes | Integer YYYYMMDD |

> Sample response

```shell
{
    "cheapest": {
        "originAirportCode": "ATL",
        "destinationAirportCode": "MIA",
        "carrierCode": "F9",
        "stops": 0,
        "price": 116.78,
        "departDate": 20200301,
        "returnDate": 20200303
    },
    "details": [
        {
            "originAirportCode": "ATL",
            "destinationAirportCode": "MIA",
            "carrierCode": "AA",
            "stops": 0,
            "price": 126.8,
            "departDate": 20200301,
            "returnDate": 20200303
        },
        {
            "originAirportCode": "ATL",
            "destinationAirportCode": "MIA",
            "carrierCode": "AA",
            "stops": 1,
            "price": 135.1,
            "departDate": 20200301,
            "returnDate": 20200303
        },
        {
            "originAirportCode": "ATL",
            "destinationAirportCode": "MIA",
            "carrierCode": "AA",
            "stops": 2,
            "price": 226.9,
            "departDate": 20200301,
            "returnDate": 20200303
        }
    ],
    "error": null
}
```

```javascript
{
    "cheapest": {
        "originAirportCode": "LAX",
        "destinationAirportCode": "SFO",
        "carrierCode": "AA",
        "stops": 0,
        "price": 48.4,
        "departDate": 20200301,
        "returnDate": 0
    },
    "details": [
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "AS",
            "stops": 0,
            "price": 48.4,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "DL",
            "stops": 0,
            "price": 48.4,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "UA",
            "stops": 0,
            "price": 48.4,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "AS",
            "stops": 1,
            "price": 131.2,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "AA",
            "stops": 1,
            "price": 185.69,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "!!",
            "stops": 1,
            "price": 242.78,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "AS",
            "stops": 2,
            "price": 250.1,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "UA",
            "stops": 1,
            "price": 298.5,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "AA",
            "stops": 2,
            "price": 421.52,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "!!",
            "stops": 2,
            "price": 560.5,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "DL",
            "stops": 2,
            "price": 565.82,
            "departDate": 20200301,
            "returnDate": 0
        },
        {
            "originAirportCode": "LAX",
            "destinationAirportCode": "SFO",
            "carrierCode": "DL",
            "stops": 1,
            "price": 599.19,
            "departDate": 20200301,
            "returnDate": 0
        }
    ],
    "error": null
}
```

**Responses**

*cheapest (the cheapest overall carrier/number of stops for the market)*

| Params | Values |
| ---- | ----------- |
| originAirportCode | IATA origin airport code |
| destinationAirportCode | IATA destination airport code |
| carrierCode | IATA validating carrier code |
| stops | Maximum number of stops |
| price | Itinerary price |
| departDate | Departure date. Format: YYYYMMDD |
| returnDate | Return date. Format: YYYYMMDD. 0 for oneway trip |

*details (repeats for each carrier/number of stops for the market)*

| Params | Values |
| ---- | ----------- |
| originAirportCode | IATA origin airport code |
| destinationAirportCode | IATA destination airport code |
| carrierCode | IATA validating carrier code |
| stops | Maximum number of stops |
| price | Itinerary price |
| departDate | Departure date. Format: YYYYMMDD |
| returnDate | Return date. Format: YYYYMMDD. 0 for oneway trip |

## getCheapestPricePerDepartDate
### ***POST***

**Summary:** Returns the cheapest price for each departure date.

**Description:** Returns the cheapest price for each departure date in a specified range for an origin / destination.

### HTTP Request
`***POST*** RealTimePricesService/getCheapestPricePerDepartDate`

> Sample request

```shell
curl -X POST \
  https://api.3victorseap.com/RealTimePricesService/getCheapestPricePerDepartDate \
  -H 'Accept: */*' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Length: 133' \
  -H 'Content-Type: application/json;charset=UTF-8' \
  -H 'Host: api.3victorseap.com' \
  -H 'Postman-Token: <TOKEN>' \
  -H 'User-Agent: PostmanRuntime/7.16.3' \
  -H 'cache-control: no-cache' \
  -H 'x-api-key: jCtEGyn3x44akvfYHOCw31NLVSHZoy3g3WYECkmm' \
  -d '{
  "origin" : "DFW",
  "destination" : "ORD",
  "roundtrip" : "true",
  "departDateStart" : 20200306,
  "departDateEnd" : 20200310
}'
```

```javascript
{
  "origin" : "YYZ",
  "destination" : "LHR",
  "roundtrip" : "false",
  "departDateStart" : 20200401,
  "departDateEnd" : 20200410
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
    "20200308": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 177.4,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 202.8,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 0,
            "price": 246.77,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 0,
            "price": 246.8,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 1,
            "price": 298.56,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "DL",
            "stops": 1,
            "price": 311.4,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 1,
            "price": 359.59,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 365.1,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "F9",
            "stops": 1,
            "price": 438.38,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AS",
            "stops": 1,
            "price": 471.4,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "!!",
            "stops": 2,
            "price": 471.9,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "!!",
            "stops": 1,
            "price": 500.6,
            "departDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 2,
            "price": 700.4,
            "departDate": 20200308
        }
    ],
    "20200309": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 0,
            "price": 147.77,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 165.6,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 176.8,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 0,
            "price": 201.8,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "DL",
            "stops": 1,
            "price": 202.39,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 1,
            "price": 203.56,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "F9",
            "stops": 1,
            "price": 254.38,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 2,
            "price": 320.4,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 1,
            "price": 344.6,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 367.4,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AS",
            "stops": 1,
            "price": 459.39,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "!!",
            "stops": 1,
            "price": 500.6,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AS",
            "stops": 2,
            "price": 554.7,
            "departDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "!!",
            "stops": 2,
            "price": 2405.38,
            "departDate": 20200309
        }
    ],
    "20200310": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 125.6,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 0,
            "price": 126.8,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "DL",
            "stops": 1,
            "price": 164.39,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 0,
            "price": 216.77,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 1,
            "price": 263.57,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "F9",
            "stops": 1,
            "price": 284.37,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 1,
            "price": 284.6,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 363.1,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 2,
            "price": 399.4,
            "departDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AS",
            "stops": 1,
            "price": 471.4,
            "departDate": 20200310
        }
    ],
    "20200306": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 154.39,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 199.8,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 0,
            "price": 231.77,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 0,
            "price": 236.79,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 1,
            "price": 287.56,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "DL",
            "stops": 1,
            "price": 301.4,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 333.1,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 2,
            "price": 379.4,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 1,
            "price": 394.6,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "F9",
            "stops": 1,
            "price": 420.38,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "DL",
            "stops": 2,
            "price": 461.7,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AS",
            "stops": 1,
            "price": 471.4,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "!!",
            "stops": 2,
            "price": 471.8,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "!!",
            "stops": 1,
            "price": 500.6,
            "departDate": 20200306
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AS",
            "stops": 2,
            "price": 537.7,
            "departDate": 20200306
        }
    ],
    "20200307": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 168.6,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 184.8,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 0,
            "price": 258.8,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 0,
            "price": 276.77,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "DL",
            "stops": 1,
            "price": 301.4,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "NK",
            "stops": 1,
            "price": 332.56,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "UA",
            "stops": 1,
            "price": 359.61,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "F9",
            "stops": 1,
            "price": 360.38,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 365.1,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "!!",
            "stops": 1,
            "price": 500.6,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "!!",
            "stops": 2,
            "price": 511.9,
            "departDate": 20200307
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AS",
            "stops": 1,
            "price": 584.42,
            "departDate": 20200307
        }
    ]
}
```

```javascript
{
    "20200404": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 335.01,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 498.41,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 544.11,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 586.9,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 650.73,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 680.42,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 690.32,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 693.0,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 695.76,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 699.86,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 699.86,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 720.78,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 721.42,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 727.21,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 2,
            "price": 734.67,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 816.21,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 816.89,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 833.17,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 834.63,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 850.41,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 2,
            "price": 856.41,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 3,
            "price": 873.47,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "MS",
            "stops": 1,
            "price": 880.31,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 882.14,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 930.26,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 955.21,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "ET",
            "stops": 1,
            "price": 1246.77,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 1326.3,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 1336.67,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 1345.4,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2544.21,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2547.6,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2558.45,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2561.48,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 1,
            "price": 2564.46,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2570.95,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 1,
            "price": 2573.55,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2578.66,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 2,
            "price": 2585.53,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 2,
            "price": 3158.69,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 2,
            "price": 3310.04,
            "departDate": 20200404
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 4074.83,
            "departDate": 20200404
        }
    ],
    "20200405": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 302.01,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 544.11,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 575.41,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 601.26,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 650.28,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 650.93,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 682.2,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 689.37,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 689.92,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 694.17,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 700.34,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 703.56,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 720.79,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 721.43,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 727.22,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 2,
            "price": 734.68,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 773.0,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 789.59,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 790.75,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 790.75,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 1,
            "price": 804.14,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 812.2,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 812.63,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 2,
            "price": 813.41,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 815.95,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 820.82,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 3,
            "price": 834.94,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 839.96,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 927.83,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "ET",
            "stops": 1,
            "price": 1252.0,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 1321.86,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2539.94,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2539.94,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2550.49,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 1,
            "price": 2556.71,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2557.04,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2569.78,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 1,
            "price": 2572.45,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2577.23,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 2,
            "price": 2583.57,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 2,
            "price": 3165.75,
            "departDate": 20200405
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 2,
            "price": 3305.38,
            "departDate": 20200405
        }
    ],
    "20200406": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 335.16,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 498.02,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 504.95,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 585.68,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 641.38,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 642.06,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 650.41,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 655.26,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 655.26,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 661.46,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 664.27,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 678.21,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 682.2,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 688.63,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 2,
            "price": 696.09,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 701.25,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 2,
            "price": 723.89,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 772.86,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 772.99,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 790.57,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 790.57,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 790.75,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 799.73,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 800.52,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 3,
            "price": 808.46,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 815.79,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 843.64,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "MS",
            "stops": 1,
            "price": 857.31,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 928.34,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2539.9,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2542.32,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2556.17,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2557.0,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2563.83,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 1,
            "price": 2567.33,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2577.45,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 1,
            "price": 2588.91,
            "departDate": 20200406
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 2894.16,
            "departDate": 20200406
        }
    ],
    "20200407": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 271.01,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 498.7,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 504.82,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 586.28,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 638.7,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 639.95,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 650.95,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 655.59,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 661.46,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 664.98,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 678.21,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 682.21,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 682.86,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 688.64,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 2,
            "price": 696.1,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 701.61,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 772.63,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 773.21,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 790.75,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 790.91,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 796.87,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 3,
            "price": 800.16,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 807.34,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 812.21,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 3,
            "price": 826.66,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 839.96,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 896.2,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 927.83,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "ET",
            "stops": 1,
            "price": 1246.77,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2539.94,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2544.21,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2554.58,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2557.21,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 1,
            "price": 2559.36,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2574.75,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 1,
            "price": 2578.2,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2579.19,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 1,
            "price": 2582.66,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 2795.86,
            "departDate": 20200407
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 2,
            "price": 3166.72,
            "departDate": 20200407
        }
    ],
    "20200401": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 247.27,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 496.19,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 575.94,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 586.27,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 639.95,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 650.41,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 651.16,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 651.25,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 655.58,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 664.21,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 664.97,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 682.2,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 682.84,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 688.63,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 2,
            "price": 696.09,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 698.67,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 2,
            "price": 729.76,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 1,
            "price": 759.4,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 770.03,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 787.66,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 790.74,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 790.74,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 799.73,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 802.95,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 806.98,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 806.98,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 2,
            "price": 813.41,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 843.8,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 927.82,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2532.98,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2532.98,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2546.79,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2558.45,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2563.83,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 1,
            "price": 2574.96,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2578.66,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 1,
            "price": 2585.64,
            "departDate": 20200401
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 3312.41,
            "departDate": 20200401
        }
    ],
    "20200402": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 248.57,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 548.85,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 586.27,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 639.75,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 680.71,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 686.36,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 688.88,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 688.88,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 689.51,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 691.77,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 694.16,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 703.55,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 720.78,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 721.42,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 727.21,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 2,
            "price": 734.67,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 814.94,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 815.43,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 830.41,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 832.64,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 833.17,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 2,
            "price": 834.94,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 843.17,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 847.16,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 849.76,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "MS",
            "stops": 1,
            "price": 857.95,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 3,
            "price": 877.71,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 886.41,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 961.63,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 1158.01,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2539.9,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2541.53,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2553.45,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2555.38,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 1,
            "price": 2558.53,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2565.35,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2575.0,
            "departDate": 20200402
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 1,
            "price": 2584.16,
            "departDate": 20200402
        }
    ],
    "20200403": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 397.01,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 541.46,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 679.87,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 688.88,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 688.88,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 689.29,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 689.37,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 692.75,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 695.76,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 703.56,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 720.79,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 721.43,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 727.22,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 2,
            "price": 735.31,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 2,
            "price": 776.01,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 1,
            "price": 809.56,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 815.94,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 815.94,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 833.19,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 833.19,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 834.94,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 2,
            "price": 840.16,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 849.78,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 850.42,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 2,
            "price": 855.94,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 3,
            "price": 873.47,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 882.14,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 889.1,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 1030.71,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "ET",
            "stops": 1,
            "price": 1253.96,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2538.31,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2539.94,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2546.79,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2557.0,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2568.96,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2577.19,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 1,
            "price": 2581.18,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 1,
            "price": 2588.4,
            "departDate": 20200403
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 3311.74,
            "departDate": 20200403
        }
    ],
    "20200408": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 366.7,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 505.99,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 549.96,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 586.9,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 650.34,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 650.34,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 651.76,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 653.31,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 656.62,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 661.53,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 665.64,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 682.59,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 683.23,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 689.02,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 695.76,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 2,
            "price": 696.49,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 2,
            "price": 731.28,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 1,
            "price": 760.97,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 2,
            "price": 773.4,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 774.47,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 790.75,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 791.19,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 792.21,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 3,
            "price": 796.79,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 801.39,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 815.89,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 815.95,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 843.41,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 2,
            "price": 848.71,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 915.15,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 930.26,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2546.87,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2547.6,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2547.6,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2561.48,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2563.18,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2577.23,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 1,
            "price": 2582.66,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 2935.26,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 2,
            "price": 3159.0,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 2,
            "price": 3307.8,
            "departDate": 20200408
        }
    ],
    "20200409": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 333.93,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 548.33,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 575.94,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 678.53,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 687.58,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 688.78,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 688.88,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 690.32,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 693.48,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 698.67,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 702.75,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 720.79,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 721.43,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 727.22,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 736.74,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 814.65,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 814.65,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 2,
            "price": 816.21,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 825.06,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 833.94,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 2,
            "price": 834.94,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 838.96,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 841.63,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 845.4,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 2,
            "price": 847.4,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "MS",
            "stops": 1,
            "price": 857.31,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 3,
            "price": 877.3,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 882.14,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 926.94,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 1335.87,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2537.49,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2544.21,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2554.58,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2559.36,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2567.42,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2575.0,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 1,
            "price": 2582.66,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 2960.68,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 2,
            "price": 3159.0,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 2,
            "price": 3303.55,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SK",
            "stops": 1,
            "price": 3936.74,
            "departDate": 20200409
        }
    ],
    "20200410": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 365.09,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 542.72,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 687.58,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 687.58,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 688.04,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 689.58,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 692.77,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 693.56,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 701.83,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 702.68,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 720.74,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 726.52,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 2,
            "price": 728.67,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 2,
            "price": 766.71,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AZ",
            "stops": 1,
            "price": 806.85,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 814.73,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 814.73,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 832.45,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 832.45,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 834.44,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 834.95,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 2,
            "price": 837.79,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 848.86,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 3,
            "price": 867.35,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SN",
            "stops": 2,
            "price": 886.41,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 889.28,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AM",
            "stops": 1,
            "price": 1004.98,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "ET",
            "stops": 1,
            "price": 1252.23,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2543.97,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2544.08,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2557.0,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2557.94,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 1,
            "price": 2560.24,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2567.42,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 2,
            "price": 2577.19,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "IB",
            "stops": 1,
            "price": 2578.2,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 1,
            "price": 2586.32,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 2,
            "price": 2929.38,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!O",
            "stops": 2,
            "price": 3165.75,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 2,
            "price": 3307.8,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SK",
            "stops": 1,
            "price": 3939.01,
            "departDate": 20200410
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

## getCheapestPricePerReturnDate
### ***POST***

**Summary:** Returns the cheapest price for each return date.

**Description:** Returns the cheapest price for a given origin, destination, and carrier for each return date between a specified departure date and ending return date.

### HTTP Request
`***POST*** RealTimePricesService/getCheapestPricePerReturnDate`

> Sample request

```shell
curl -X POST \
  https://api.3victorseap.com/RealTimePricesService/getCheapestPricePerReturnDate \
  -H 'Accept: */*' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Length: 128' \
  -H 'Content-Type: application/json;charset=UTF-8' \
  -H 'Host: api.3victorseap.com' \
  -H 'Postman-Token: <TOKEN>' \
  -H 'User-Agent: PostmanRuntime/7.16.3' \
  -H 'cache-control: no-cache' \
  -H 'x-api-key: jCtEGyn3x44akvfYHOCw31NLVSHZoy3g3WYECkmm' \
  -d '{
  "origin" : "DFW",
  "destination" : "ORD",
  "carrierCode" : "AA",
  "departDate" : 20200306,
  "returnDateEnd" : 20200311
}'
```

```javascript
{
  "origin" : "MEX",
  "destination" : "CUN",
  "carrierCode" : "AM",
  "departDate" : 20200401,
  "returnDateEnd" : 20200411
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
    "20200308": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 211.6,
            "departDate": 20200306,
            "returnDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 271.8,
            "departDate": 20200306,
            "returnDate": 20200308
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 403.1,
            "departDate": 20200306,
            "returnDate": 20200308
        }
    ],
    "20200309": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 220.4,
            "departDate": 20200306,
            "returnDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 247.8,
            "departDate": 20200306,
            "returnDate": 20200309
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 363.1,
            "departDate": 20200306,
            "returnDate": 20200309
        }
    ],
    "20200310": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 188.59,
            "departDate": 20200306,
            "returnDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 199.8,
            "departDate": 20200306,
            "returnDate": 20200310
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 333.1,
            "departDate": 20200306,
            "returnDate": 20200310
        }
    ],
    "20200311": [
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 1,
            "price": 177.4,
            "departDate": 20200306,
            "returnDate": 20200311
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 0,
            "price": 202.8,
            "departDate": 20200306,
            "returnDate": 20200311
        },
        {
            "originAirportCode": "DFW",
            "destinationAirportCode": "ORD",
            "carrierCode": "AA",
            "stops": 2,
            "price": 421.1,
            "departDate": 20200306,
            "returnDate": 20200311
        }
    ]
}
```

```javascript
{
    "20200404": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 145.26,
            "departDate": 20200401,
            "returnDate": 20200404
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 2,
            "price": 409.83,
            "departDate": 20200401,
            "returnDate": 20200404
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 1,
            "price": 474.98,
            "departDate": 20200401,
            "returnDate": 20200404
        }
    ],
    "20200405": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 145.09,
            "departDate": 20200401,
            "returnDate": 20200405
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 1,
            "price": 360.33,
            "departDate": 20200401,
            "returnDate": 20200405
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 2,
            "price": 395.64,
            "departDate": 20200401,
            "returnDate": 20200405
        }
    ],
    "20200406": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 165.38,
            "departDate": 20200401,
            "returnDate": 20200406
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 1,
            "price": 360.6,
            "departDate": 20200401,
            "returnDate": 20200406
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 2,
            "price": 397.36,
            "departDate": 20200401,
            "returnDate": 20200406
        }
    ],
    "20200407": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 145.09,
            "departDate": 20200401,
            "returnDate": 20200407
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 2,
            "price": 395.22,
            "departDate": 20200401,
            "returnDate": 20200407
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 1,
            "price": 419.62,
            "departDate": 20200401,
            "returnDate": 20200407
        }
    ],
    "20200401": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 229.02,
            "departDate": 20200401,
            "returnDate": 20200401
        }
    ],
    "20200402": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 199.9,
            "departDate": 20200401,
            "returnDate": 20200402
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 2,
            "price": 301.79,
            "departDate": 20200401,
            "returnDate": 20200402
        }
    ],
    "20200403": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 169.45,
            "departDate": 20200401,
            "returnDate": 20200403
        }
    ],
    "20200408": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 144.93,
            "departDate": 20200401,
            "returnDate": 20200408
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 1,
            "price": 407.36,
            "departDate": 20200401,
            "returnDate": 20200408
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 2,
            "price": 463.74,
            "departDate": 20200401,
            "returnDate": 20200408
        }
    ],
    "20200409": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 145.02,
            "departDate": 20200401,
            "returnDate": 20200409
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 2,
            "price": 396.11,
            "departDate": 20200401,
            "returnDate": 20200409
        }
    ],
    "20200410": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 174.31,
            "departDate": 20200401,
            "returnDate": 20200410
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 1,
            "price": 419.99,
            "departDate": 20200401,
            "returnDate": 20200410
        },
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 2,
            "price": 463.74,
            "departDate": 20200401,
            "returnDate": 20200410
        }
    ],
    "20200411": [
        {
            "originAirportCode": "MEX",
            "destinationAirportCode": "CUN",
            "carrierCode": "AM",
            "stops": 0,
            "price": 544.09,
            "departDate": 20200401,
            "returnDate": 20200411
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

## getMeOutOfTown
### ***POST***

**Summary:** Returns weekend deals from an origin.

**Description:** Returns weekend deals from an origin. Weekend departures are Thursday, Friday, and Saturday. 

### HTTP Request
`***POST*** RealTimePricesService/getMeOutOfTown`

> Sample request

```shell
curl -X POST \
  https://api.3victorseap.com/RealTimePricesService/getMeOutOfTown \
  -H 'Accept: */*' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Length: 73' \
  -H 'Content-Type: application/json;charset=UTF-8' \
  -H 'Host: api.3victorseap.com' \
  -H 'Postman-Token: <TOKEN>' \
  -H 'User-Agent: PostmanRuntime/7.16.3' \
  -H 'cache-control: no-cache' \
  -H 'x-api-key: jCtEGyn3x44akvfYHOCw31NLVSHZoy3g3WYECkmm' \
  -d '{
  "origin" : "SEA",
  "destinations" : ["GEG","SLC"],
  "weekend" : 2
}'
```

```javascript
{
  "origin" : "LAS",
  "destinations" : ["LAX","ONT","SNA","SAT","OAK","DEN","SJC","BUR"],
  "weekend" : 2
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
    "GEG": [
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "AS",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "DL",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "AS",
            "stops": 2,
            "price": 194.9,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "AS",
            "stops": 1,
            "price": 195.1,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "!!",
            "stops": 0,
            "price": 246.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "!!",
            "stops": 1,
            "price": 295.1,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "!!",
            "stops": 2,
            "price": 364.9,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "DL",
            "stops": 1,
            "price": 520.61,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "GEG",
            "carrierCode": "DL",
            "stops": 2,
            "price": 540.41,
            "departDate": 20200124,
            "returnDate": 20200126
        }
    ],
    "SLC": [
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "DL",
            "stops": 0,
            "price": 176.78,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "AS",
            "stops": 0,
            "price": 176.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "AS",
            "stops": 0,
            "price": 176.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "AS",
            "stops": 1,
            "price": 206.6,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "AS",
            "stops": 1,
            "price": 206.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "DL",
            "stops": 1,
            "price": 236.1,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "AS",
            "stops": 2,
            "price": 249.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "!!",
            "stops": 1,
            "price": 251.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "AA",
            "stops": 1,
            "price": 293.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "AA",
            "stops": 2,
            "price": 307.7,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "UA",
            "stops": 1,
            "price": 308.4,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "!!",
            "stops": 2,
            "price": 317.4,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "SEA",
            "destinationAirportCode": "SLC",
            "carrierCode": "UA",
            "stops": 2,
            "price": 344.7,
            "departDate": 20200123,
            "returnDate": 20200127
        }
    ]
}
```

```javascript
{
    "LAX": [
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "F9",
            "stops": 0,
            "price": 66.79,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "AA",
            "stops": 0,
            "price": 72.8,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "AA",
            "stops": 0,
            "price": 72.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "AA",
            "stops": 0,
            "price": 72.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "AS",
            "stops": 0,
            "price": 86.81,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "DL",
            "stops": 0,
            "price": 88.8,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "AA",
            "stops": 1,
            "price": 98.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 1,
            "price": 105.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 1,
            "price": 105.6,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "NK",
            "stops": 0,
            "price": 114.78,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "NK",
            "stops": 0,
            "price": 114.78,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "NK",
            "stops": 0,
            "price": 114.78,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "AS",
            "stops": 1,
            "price": 129.6,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "DL",
            "stops": 1,
            "price": 145.57,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "AA",
            "stops": 2,
            "price": 158.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "!!",
            "stops": 0,
            "price": 172.63,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "!!",
            "stops": 1,
            "price": 235.6,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "!!",
            "stops": 2,
            "price": 346.4,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 2,
            "price": 383.4,
            "departDate": 20200125,
            "returnDate": 20200126
        }
    ],
    "ONT": [
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "ONT",
            "carrierCode": "AA",
            "stops": 1,
            "price": 130.6,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "ONT",
            "carrierCode": "AA",
            "stops": 2,
            "price": 218.7,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "ONT",
            "carrierCode": "AS",
            "stops": 1,
            "price": 219.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "ONT",
            "carrierCode": "UA",
            "stops": 1,
            "price": 317.4,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "ONT",
            "carrierCode": "!!",
            "stops": 1,
            "price": 467.4,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "ONT",
            "carrierCode": "!!",
            "stops": 1,
            "price": 467.4,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "ONT",
            "carrierCode": "!!",
            "stops": 2,
            "price": 503.7,
            "departDate": 20200124,
            "returnDate": 20200126
        }
    ],
    "SAT": [
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "AA",
            "stops": 1,
            "price": 144.4,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "AA",
            "stops": 1,
            "price": 144.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "AA",
            "stops": 2,
            "price": 158.69,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "UA",
            "stops": 1,
            "price": 238.4,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "UA",
            "stops": 1,
            "price": 238.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "DL",
            "stops": 1,
            "price": 238.4,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "F9",
            "stops": 1,
            "price": 257.38,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "AS",
            "stops": 1,
            "price": 322.4,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "AS",
            "stops": 1,
            "price": 322.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "DL",
            "stops": 2,
            "price": 353.69,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "AS",
            "stops": 2,
            "price": 363.7,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "!!",
            "stops": 1,
            "price": 457.43,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SAT",
            "carrierCode": "!!",
            "stops": 2,
            "price": 2374.8,
            "departDate": 20200124,
            "returnDate": 20200128
        }
    ],
    "SNA": [
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "F9",
            "stops": 0,
            "price": 66.8,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "F9",
            "stops": 0,
            "price": 66.8,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "F9",
            "stops": 0,
            "price": 66.8,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "F9",
            "stops": 0,
            "price": 66.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "F9",
            "stops": 0,
            "price": 66.8,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "DL",
            "stops": 0,
            "price": 106.85,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "AS",
            "stops": 1,
            "price": 139.6,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "AA",
            "stops": 1,
            "price": 141.6,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "UA",
            "stops": 1,
            "price": 158.4,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "UA",
            "stops": 1,
            "price": 158.4,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "DL",
            "stops": 1,
            "price": 200.72,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "AA",
            "stops": 2,
            "price": 210.69,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "!!",
            "stops": 0,
            "price": 242.65,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "!!",
            "stops": 0,
            "price": 242.65,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "!!",
            "stops": 0,
            "price": 242.65,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "!!",
            "stops": 1,
            "price": 264.6,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "B6",
            "stops": 0,
            "price": 378.21,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "UA",
            "stops": 2,
            "price": 432.7,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SNA",
            "carrierCode": "!!",
            "stops": 2,
            "price": 494.7,
            "departDate": 20200124,
            "returnDate": 20200126
        }
    ],
    "OAK": [
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "NK",
            "stops": 0,
            "price": 115.78,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "NK",
            "stops": 0,
            "price": 115.78,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "AA",
            "stops": 1,
            "price": 142.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "DL",
            "stops": 1,
            "price": 147.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "AA",
            "stops": 2,
            "price": 162.7,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "B6",
            "stops": 1,
            "price": 166.41,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "NK",
            "stops": 1,
            "price": 171.57,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "AS",
            "stops": 1,
            "price": 182.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "DL",
            "stops": 2,
            "price": 225.7,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "B6",
            "stops": 0,
            "price": 268.2,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "LF",
            "stops": 1,
            "price": 338.4,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "LF",
            "stops": 1,
            "price": 338.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "!!",
            "stops": 1,
            "price": 358.4,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "!!",
            "stops": 1,
            "price": 358.4,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "!!",
            "stops": 1,
            "price": 358.4,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "!!",
            "stops": 1,
            "price": 358.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "!!",
            "stops": 2,
            "price": 367.2,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "!!",
            "stops": 2,
            "price": 367.2,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "!!",
            "stops": 2,
            "price": 367.2,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "OAK",
            "carrierCode": "AS",
            "stops": 2,
            "price": 450.7,
            "departDate": 20200124,
            "returnDate": 20200127
        }
    ],
    "DEN": [
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "F9",
            "stops": 0,
            "price": 78.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "F9",
            "stops": 0,
            "price": 78.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200124,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "UA",
            "stops": 0,
            "price": 96.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "AA",
            "stops": 1,
            "price": 114.4,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "AA",
            "stops": 1,
            "price": 114.4,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "AA",
            "stops": 1,
            "price": 114.4,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "AA",
            "stops": 2,
            "price": 118.7,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "NK",
            "stops": 0,
            "price": 124.78,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "NK",
            "stops": 0,
            "price": 124.78,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "NK",
            "stops": 0,
            "price": 124.78,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "DL",
            "stops": 1,
            "price": 144.4,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "DL",
            "stops": 1,
            "price": 144.4,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "NK",
            "stops": 1,
            "price": 169.56,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "NK",
            "stops": 1,
            "price": 169.56,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "AS",
            "stops": 1,
            "price": 212.4,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "UA",
            "stops": 1,
            "price": 226.6,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "UA",
            "stops": 1,
            "price": 226.6,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "NK",
            "stops": 2,
            "price": 237.35,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "NK",
            "stops": 2,
            "price": 237.35,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "NK",
            "stops": 2,
            "price": 237.35,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "AS",
            "stops": 2,
            "price": 257.7,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "DL",
            "stops": 2,
            "price": 260.7,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "UA",
            "stops": 2,
            "price": 274.4,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "!!",
            "stops": 2,
            "price": 353.7,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "DEN",
            "carrierCode": "!!",
            "stops": 1,
            "price": 370.4,
            "departDate": 20200124,
            "returnDate": 20200128
        }
    ],
    "SJC": [
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "F9",
            "stops": 0,
            "price": 86.8,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "F9",
            "stops": 0,
            "price": 86.8,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "F9",
            "stops": 0,
            "price": 86.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "F9",
            "stops": 0,
            "price": 86.8,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "DL",
            "stops": 0,
            "price": 106.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "AA",
            "stops": 1,
            "price": 124.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "AS",
            "stops": 1,
            "price": 125.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "DL",
            "stops": 1,
            "price": 125.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "AA",
            "stops": 2,
            "price": 177.7,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "UA",
            "stops": 1,
            "price": 199.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "B6",
            "stops": 1,
            "price": 205.56,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "DL",
            "stops": 2,
            "price": 241.4,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200124,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 0,
            "price": 261.8,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "!!",
            "stops": 1,
            "price": 307.4,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "SJC",
            "carrierCode": "UA",
            "stops": 2,
            "price": 418.7,
            "departDate": 20200130,
            "returnDate": 20200203
        }
    ],
    "BUR": [
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200124,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "NK",
            "stops": 0,
            "price": 86.79,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 124.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 124.4,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "AA",
            "stops": 2,
            "price": 168.69,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "AA",
            "stops": 2,
            "price": 168.69,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "AS",
            "stops": 1,
            "price": 179.6,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "B6",
            "stops": 0,
            "price": 187.19,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "B6",
            "stops": 0,
            "price": 187.19,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 308.4,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 308.4,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 308.4,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 308.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 308.4,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "AS",
            "stops": 2,
            "price": 343.4,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 477.4,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 528.7,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "LAS",
            "destinationAirportCode": "BUR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 528.7,
            "departDate": 20200124,
            "returnDate": 20200126
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
