# GET/tableNo 

Method | syntax
----- | ----------
GET | URL/{tableNo}


## Description
Gets the bill for a specific table number.

### Query Parameters

Name | Description
---- | --------------------
ID | The table number. The default is 99, the value for take-out orders. For POC stage, this is the only available value. 

## Examples

### Request

```curl
curl -X GET "http://URL/tableNo?id=99"

```

### Response

```JSON
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

### Response Schema
Name | type | Description
---- | ----- | ----- 
orderNum | int |  The order number.  
timestamp | string |  The time of the order, represented in Eastern Standard Time (EST). All dates are in ISO 8601 format: YYYY-MM-DDThh:mmTZD.  
{Itemn} | object |  The nth meal item  the customer ordered. For the first item, n=1 (item1), for the second n=2 (item2), etc.
{Itemn}/{ItemOrdered} | object | An object containing the meal type and cost.  
{Itemn}/{ItemOrdered}/type | string |  The meal type. For  the purposes of the PoC, the available meal types are "burgerMeal" and "salad".  
Cost | float |  the price of the item.  
