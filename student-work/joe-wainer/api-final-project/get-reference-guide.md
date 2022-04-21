# GET Reference Guide

# tableNo Endpoint

| Method | Syntax |
| --- | --- |
| GET | http://URL/tableNo |

## GET/tableNo

This is the call sent when a staff member wants to get the bill. The GET request must include the table number. Order numbers are included in the response. When this is printed, the customer can pay the bill.

## Response Schema

| Name | Type | Description |
| --- | --- | --- |
| orderNum | integer | Unique number identifying the order. Take out orders are table 99. |
| timestamp | string | Date and time of the order (UTC). |
| Item | object | Object containing details of the meal. |
| ItemOrdered | string | The requested order. Can be either “burgerMeal” or “salad”. |
| cost | float | Price of each ordered meal. |

## Example

### Request

```http
HTTP curl -X GET "http://URL/tableNo?id=99"
```

### response

```json
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
