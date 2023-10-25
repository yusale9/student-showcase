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

#### Query parameters

| Query parameter | Type | Required? | Description                             |
|-----------------|------|-----------|-----------------------------------------|
| id | int  | Required  | Table number assigned to order. Value must be between 0 and 100. Default value is 0. |

### Request example

```
curl -X GET 'http://api.acmo.com/tableNo?id=99'
```

### Response
Returns a JSON object with the following properties:

| Attribute | Type   | Required? | Description                  |
|-----------|--------|-----------|------------------------------|
| orderNum  | int | Required  | System generated number assigned to order. |
| timestamp | string | Required  | Time and date order is retrieved in ISO 8601 format. |
| Item | object | Required | Contains an ItemOrdered object. Each Item is identified by a number.|
| ItemOrdered | object | Required  | Contains type and cost of the item ordered. |
| type | string | Required  | Name of menu item ordered. |
| Cost | int | Required  | Cost of menu item ordered. |

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
| `200 OK`    | Request successful. | Order has been retrieved and bill is printing. |
| `404 Not Found` | Order not found. | Order number could not be located. A manager has removed the order from the system or the bill has already been paid. |
| `503 Service Unavailable` | Server error. | Server is down and bill can not be printed at this time. |

---
