# AppCorp Meal Order API Reference

## Overview

This is an API to order take out meals.

### Base URL

```
https://api.acmo.com
```

## Retrieve the bill

### Endpoint

```
GET /tableNo
```

### Description

Retrieves the customer's order and returns a bill of sale. 

### Request schema

#### Path parameters

| Path parameter | Type   | Required? | Description                  |
|----------------|--------|-----------|------------------------------|
| {id}           | string | Required  | {Unique identifier of user}  |
|                |        |           |                              |


#### Request body

{This section is optional.}

| Field  | Type   | Required? | Description                      |
|--------|--------|-----------|----------------------------------|
| {id}   | string | Required  | {Unique identifier of the user}  |
| {name} | string | Optional  | {Name of the user}               |


### Request example

```
curl -X GET 'http://api.acmo.com/tableNo?id-99'
```

### Response
Returns a JSON object with the following properties:

| Attribute | Type   | Required? | Description                  |
|-----------|--------|-----------|------------------------------|
| orderNum  | int | Required  | {Unique identifier of user}  |
| timestamp | date | Required  | {Name of user}               |
| Items | array | Required | Contains a list of the items ordered. Each item is an object containing additional information. |
| ItemOrdered | array | Required  | Contains the details of an item. Each itemOrdered is an object containing additional information. |
| type | string | Required  | The name of the menu item ordered. |
| Cost | int | Required  | The cost of the menu item ordered. |

### Response example

```
{
   "orderNum":123,
   "timestamp":"2020-01-21T07:44:45-05:00",
   "Item1":{
     "ItemOrdered":{
     "type":"burgerMeal",
     "Cost":10.99
     }
   },
   "Item2":{
     "ItemOrdered":{
     "type":"salad",
     "Cost":9.50
     }
  }
}
```

### Response codes

The Meal Order API uses the following standard HTTP response codes:

| Status code | Message           | Description   |
|-------------|-------------------|---------------|
| `200 OK`    | Request successful. | Order has been retrived and bill is printing. |
| `404 Not Found` | Order not found. | Order number could not be located. A manager has removed the order from the system or the bill has already been paid. |
| `503 Service Unavailable` | Server error. | Server is down and bill can not be printed at this time. |

---
