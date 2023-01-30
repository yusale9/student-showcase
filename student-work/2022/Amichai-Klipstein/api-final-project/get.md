# GET Request: Get Bill

Method | syntax
----- | ----------
GET | http://URL/tableNo?id

## Description
The cashier uses this GET request to retrieve data for billing.

### Request Parameters
Each order is calculated per table. Takeaways are table "99".
Name | Type | Req. | Description | Default
-----|------|------|-------------|-------------
tableNo| int | Y | the table that made the order | 99 
### Response Parameters
Name | Type | Req. | Description
---- | ----- | ----- | --------------------
orderNum | int | Y |  number of the order
timeStamp | datetime  | Y | time and date of the order

#### JSON Object: Items
Each ordered item adds a new parameter. The items are numbered according  
to their place in the order. For example: item1 first, then item2 etc. Each item  
 includes the type of the item and time and date of the order.  
**Note:** All prices are in USD.
Name | Type | Req.  | Description 
-----|------|-------|-------------
type | string | Y | the meal you ordered 
cost | string | Y | the total price of the meal


## Examples

### Request

```CURL
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

<!-- Write a comment explaining the response, if it would be helpful. For a response with a complicated schema, create a table like the one used above for the request.  -->
