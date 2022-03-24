# Bill

Method | syntax
----- | ----------
GET | /bill


## Description

Receives a table number and returns that table's bill including a list of all items ordered. 

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
timestamp | ISO 8601 timestamp | The date and time when the app generated the bill.
totalCost | float | The total cost of all the items on the bill.
items | Array\<item\> | An array of `item` objects representing all the items on the bill.
   
##### Item Object

Name | type | Description
-----| -----| -----------
item | string | The menu item.
price | float | The menu item's price.

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
      "price": 10.99
    },
    {
      "item": "salad",
      "price": 9.50
    }
  ]
}
```
