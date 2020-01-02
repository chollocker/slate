---

title: 3Victors API Documents

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

# Introduction

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

# RealTimePricesService/getCheapestPriceForTrip
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

# RealTimePricesService/getCheapestPricePerDepartDate
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


# /PET/FINDBYSTATUS
## ***GET***

**Summary:** Finds Pets by status

**Description:** Multiple status values can be provided with comma separated strings

### HTTP Request
`***GET*** /pet/findByStatus`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| status | query | Status values that need to be considered for filter | Yes | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid status value |

# /PET/FINDBYTAGS
## ***GET***

**Summary:** Finds Pets by tags

**Description:** Muliple tags can be provided with comma separated strings. Use         tag1, tag2, tag3 for testing.

### HTTP Request
`***GET*** /pet/findByTags`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| tags | query | Tags to filter by | Yes | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid tag value |

# /PET/{PETID}
## ***GET***

**Summary:** Find pet by ID

**Description:** Returns a single pet

### HTTP Request
`***GET*** /pet/{petId}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to return | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Pet not found |

## ***POST***

**Summary:** Updates a pet in the store with form data

**Description:**

### HTTP Request
`***POST*** /pet/{petId}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet that needs to be updated | Yes | long |
| name | formData | Updated name of the pet | No | string |
| status | formData | Updated status of the pet | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 405 | Invalid input |

## ***DELETE***

**Summary:** Deletes a pet

**Description:**

### HTTP Request
`***DELETE*** /pet/{petId}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| api_key | header |  | No | string |
| petId | path | Pet id to delete | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Pet not found |

# /PET/{PETID}/UPLOADIMAGE
## ***POST***

**Summary:** uploads an image

**Description:**

### HTTP Request
`***POST*** /pet/{petId}/uploadImage`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to update | Yes | long |
| additionalMetadata | formData | Additional data to pass to server | No | string |
| file | formData | file to upload | No | file |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

# /STORE/INVENTORY
## ***GET***

**Summary:** Returns pet inventories by status

**Description:** Returns a map of status codes to quantities

### HTTP Request
`***GET*** /store/inventory`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

# /STORE/ORDER
## ***POST***

**Summary:** Place an order for a pet

**Description:**

### HTTP Request
`***POST*** /store/order`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | order placed for purchasing the pet | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid Order |

# /STORE/ORDER/{ORDERID}
## ***GET***

**Summary:** Find purchase order by ID

**Description:** For valid response try integer IDs with value >= 1 and <= 10.         Other values will generated exceptions

### HTTP Request
`***GET*** /store/order/{orderId}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of pet that needs to be fetched | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Order not found |

## ***DELETE***

**Summary:** Delete purchase order by ID

**Description:** For valid response try integer IDs with positive integer value.         Negative or non-integer values will generate API errors

### HTTP Request
`***DELETE*** /store/order/{orderId}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of the order that needs to be deleted | Yes | long |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Order not found |

# /USER
## ***POST***

**Summary:** Create user

**Description:** This can only be done by the logged in user.

### HTTP Request
`***POST*** /user`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | Created user object | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /USER/CREATEWITHARRAY
## ***POST***

**Summary:** Creates list of users with given input array

**Description:**

### HTTP Request
`***POST*** /user/createWithArray`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | List of user object | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /USER/CREATEWITHLIST
## ***POST***

**Summary:** Creates list of users with given input array

**Description:**

### HTTP Request
`***POST*** /user/createWithList`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | List of user object | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /USER/LOGIN
## ***GET***

**Summary:** Logs user into the system

**Description:**

### HTTP Request
`***GET*** /user/login`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | query | The user name for login | Yes | string |
| password | query | The password for login in clear text | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username/password supplied |

# /USER/LOGOUT
## ***GET***

**Summary:** Logs out current logged in user session

**Description:**

### HTTP Request
`***GET*** /user/logout`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /USER/{USERNAME}
## ***GET***

**Summary:** Get user by user name

**Description:**

### HTTP Request
`***GET*** /user/{username}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be fetched. Use user1 for testing.  | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username supplied |
| 404 | User not found |

## ***PUT***

**Summary:** Updated user

**Description:** This can only be done by the logged in user.

### HTTP Request
`***PUT*** /user/{username}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | name that need to be updated | Yes | string |
| body | body | Updated user object | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid user supplied |
| 404 | User not found |

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
