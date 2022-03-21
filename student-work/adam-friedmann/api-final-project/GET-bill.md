# Bill

Method | syntax
----- | ----------
GET | https://api.putnamdiner.com/bill


## Description

Receives a table number and returns that table's bill including the details of all items ordered. 

> **Note**  
> The app closes any orders associated with a table after generating a bill.

### Query Parameters

Name | type | Req. | Description
---- | ----- | ----- | --------------------
tableNumber | int | Y |  The table number for the desired bill. The number for takeout orders is `99`.

### Response

When a request succeeds, the response body includes the following object.

#### Response Object

Name | type | Description
-----| -----| -----------
orderNumber | int | The order ID number used to generate the bill.
timestamp | ISO 8601 timestamp | The date and time when the bill was generated.
totalCost | float | The total cost of all the items on the bill.
items | Array\<item\> | An array of `item` objects representing all the items on the bill.
   
##### Item Object

Name | type | Description
-----| -----| -----------
item | string | The menu item.
cost | float | The menu item's cost.

#### Response Codes

Code | Meaning
-----| -------
200  | OK: The request succeeded. The response body contains the requested table's bill.
404  | Not Found: Either the table number doesn't exist, or the requested table doesn't have an open order.
500  | Error: Internal server error

## Examples

### Request

Sample request using cURL:

```BASH
curl -XGET 'https://putnamapp.com/bill?tableNumber=12'
```


### Response

Sample response object:

```JSON
{
  "orderNumber": 123,
  "timestamp": "2020-01-21T07:44:45-05:00",
  "totalCost" : 20.49,
  "items": [
    {
      "item": "burgerMeal",
      "cost": 10.99
    },
    {
      "item": "salad",
      "cost": 9.50
    }
  ]
}
```
