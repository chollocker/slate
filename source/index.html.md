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
  "departDateStart" : 20200408,
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
    "20200408": [
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TP",
            "stops": 1,
            "price": 366.01,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 505.11,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 549.41,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 2,
            "price": 586.36,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 1,
            "price": 642.01,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 650.81,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 651.16,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 651.16,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 651.16,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 651.16,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 655.66,
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
            "carrierCode": "!T",
            "stops": 2,
            "price": 696.49,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 706.61,
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
            "stops": 0,
            "price": 772.86,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 772.86,
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
            "carrierCode": "LH",
            "stops": 1,
            "price": 790.57,
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
            "stops": 0,
            "price": 790.91,
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
            "price": 799.8,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 807.04,
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
            "price": 905.06,
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
            "carrierCode": "AA",
            "stops": 0,
            "price": 2542.32,
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
            "carrierCode": "BA",
            "stops": 1,
            "price": 2549.29,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 0,
            "price": 2559.36,
            "departDate": 20200408
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 2565.62,
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
            "price": 338.81,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "TK",
            "stops": 1,
            "price": 548.49,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 572.62,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 678.99,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 2,
            "price": 678.99,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 685.73,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 688.04,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 689.16,
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
            "price": 695.71,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 701.79,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 706.88,
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
            "carrierCode": "TK",
            "stops": 2,
            "price": 737.36,
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
            "stops": 0,
            "price": 831.2,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 831.2,
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
            "carrierCode": "AC",
            "stops": 0,
            "price": 840.1,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 840.1,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 842.64,
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
            "carrierCode": "LX",
            "stops": 1,
            "price": 850.06,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "MS",
            "stops": 1,
            "price": 858.61,
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
            "price": 928.81,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 948.79,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 2,
            "price": 960.7,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AY",
            "stops": 0,
            "price": 2532.54,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2541.08,
            "departDate": 20200409
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2548.5,
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
            "carrierCode": "BA",
            "stops": 0,
            "price": 2581.88,
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
            "price": 363.87,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "FI",
            "stops": 1,
            "price": 542.35,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 676.7,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "VS",
            "stops": 1,
            "price": 685.73,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 2,
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
            "carrierCode": "AF",
            "stops": 1,
            "price": 690.44,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "EI",
            "stops": 1,
            "price": 691.23,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AF",
            "stops": 2,
            "price": 695.04,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!T",
            "stops": 1,
            "price": 699.47,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "KL",
            "stops": 1,
            "price": 699.47,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 716.22,
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
            "price": 806.31,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "!A",
            "stops": 1,
            "price": 811.99,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 0,
            "price": 811.99,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AC",
            "stops": 1,
            "price": 811.99,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 1,
            "price": 829.66,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LH",
            "stops": 0,
            "price": 829.66,
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
            "carrierCode": "UA",
            "stops": 1,
            "price": 838.82,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "LX",
            "stops": 1,
            "price": 846.01,
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
            "carrierCode": "AY",
            "stops": 0,
            "price": 2532.54,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 2544.21,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "BA",
            "stops": 1,
            "price": 2553.23,
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
            "carrierCode": "BA",
            "stops": 0,
            "price": 2562.59,
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
            "carrierCode": "LX",
            "stops": 2,
            "price": 3448.03,
            "departDate": 20200410
        },
        {
            "originAirportCode": "YYZ",
            "destinationAirportCode": "LHR",
            "carrierCode": "SK",
            "stops": 1,
            "price": 3920.75,
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
  "origin" : "PHX",
  "destinations" : ["LAX","ONT","SNA","LGB","BUR"],
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
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 0,
            "price": 126.8,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "AA",
            "stops": 0,
            "price": 126.8,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 1,
            "price": 135.6,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "AA",
            "stops": 1,
            "price": 135.6,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "DL",
            "stops": 0,
            "price": 136.79,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "DL",
            "stops": 0,
            "price": 136.79,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "F9",
            "stops": 1,
            "price": 192.39,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "F9",
            "stops": 1,
            "price": 192.39,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "DL",
            "stops": 1,
            "price": 201.24,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "AS",
            "stops": 1,
            "price": 257.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "!!",
            "stops": 1,
            "price": 262.4,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "UA",
            "stops": 2,
            "price": 268.4,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "!!",
            "stops": 2,
            "price": 276.7,
            "departDate": 20200125,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "AS",
            "stops": 2,
            "price": 307.7,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "!!",
            "stops": 0,
            "price": 451.76,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LAX",
            "carrierCode": "AA",
            "stops": 2,
            "price": 1101.4,
            "departDate": 20200124,
            "returnDate": 20200126
        }
    ],
    "ONT": [
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "AA",
            "stops": 0,
            "price": 169.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "F9",
            "stops": 1,
            "price": 172.37,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "F9",
            "stops": 1,
            "price": 172.37,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "AA",
            "stops": 1,
            "price": 178.6,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "AA",
            "stops": 1,
            "price": 178.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "AS",
            "stops": 1,
            "price": 262.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "!!",
            "stops": 1,
            "price": 287.38,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "AS",
            "stops": 2,
            "price": 312.7,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "UA",
            "stops": 1,
            "price": 358.4,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "DL",
            "stops": 1,
            "price": 361.49,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "UA",
            "stops": 2,
            "price": 428.7,
            "departDate": 20200123,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "!!",
            "stops": 2,
            "price": 533.7,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "ONT",
            "carrierCode": "!!",
            "stops": 2,
            "price": 533.7,
            "departDate": 20200124,
            "returnDate": 20200127
        }
    ],
    "LGB": [
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LGB",
            "carrierCode": "AA",
            "stops": 0,
            "price": 172.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LGB",
            "carrierCode": "AA",
            "stops": 0,
            "price": 172.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LGB",
            "carrierCode": "AA",
            "stops": 1,
            "price": 181.6,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LGB",
            "carrierCode": "AA",
            "stops": 1,
            "price": 181.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LGB",
            "carrierCode": "DL",
            "stops": 1,
            "price": 338.4,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LGB",
            "carrierCode": "!!",
            "stops": 1,
            "price": 440.41,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "LGB",
            "carrierCode": "!!",
            "stops": 2,
            "price": 835.58,
            "departDate": 20200124,
            "returnDate": 20200126
        }
    ],
    "SNA": [
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "F9",
            "stops": 1,
            "price": 192.4,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "F9",
            "stops": 1,
            "price": 192.4,
            "departDate": 20200125,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "F9",
            "stops": 1,
            "price": 192.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "AA",
            "stops": 0,
            "price": 199.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "AA",
            "stops": 1,
            "price": 208.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "AA",
            "stops": 1,
            "price": 208.6,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "AS",
            "stops": 1,
            "price": 267.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "!!",
            "stops": 2,
            "price": 306.68,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "AS",
            "stops": 2,
            "price": 317.7,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "DL",
            "stops": 2,
            "price": 336.69,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "UA",
            "stops": 1,
            "price": 350.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "DL",
            "stops": 1,
            "price": 354.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "!!",
            "stops": 1,
            "price": 407.4,
            "departDate": 20200124,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "SNA",
            "carrierCode": "UA",
            "stops": 2,
            "price": 426.69,
            "departDate": 20200130,
            "returnDate": 20200202
        }
    ],
    "BUR": [
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 141.8,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "AA",
            "stops": 0,
            "price": 141.8,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 150.6,
            "departDate": 20200130,
            "returnDate": 20200202
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "AA",
            "stops": 1,
            "price": 150.6,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "DL",
            "stops": 1,
            "price": 198.41,
            "departDate": 20200123,
            "returnDate": 20200128
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "B6",
            "stops": 0,
            "price": 207.4,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "AS",
            "stops": 1,
            "price": 267.4,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "AS",
            "stops": 2,
            "price": 317.7,
            "departDate": 20200130,
            "returnDate": 20200203
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "UA",
            "stops": 1,
            "price": 424.4,
            "departDate": 20200130,
            "returnDate": 20200204
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "!!",
            "stops": 1,
            "price": 427.31,
            "departDate": 20200125,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "UA",
            "stops": 2,
            "price": 480.7,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "!!",
            "stops": 2,
            "price": 521.7,
            "departDate": 20200123,
            "returnDate": 20200127
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "UA",
            "stops": 3,
            "price": 661.0,
            "departDate": 20200124,
            "returnDate": 20200126
        },
        {
            "originAirportCode": "PHX",
            "destinationAirportCode": "BUR",
            "carrierCode": "!!",
            "stops": 3,
            "price": 890.0,
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
