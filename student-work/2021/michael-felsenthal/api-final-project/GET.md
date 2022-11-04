# GET Reference type

Method | syntax
----- | ----------
GET | base_url/endpoint/etc.


## Parameters

Name | type | Req. | Description
---- | ----- | ----- | --------------------
Parameter_one | string | Y |  Meal Type. Either says "burgerMeal" or "salad"
Parameter_two | int float  | N | Timestamp for order 
Parameter_three | int  | Y | Cost 

# Example
The following example will retrieve an order from a customer:
``curl -X GET "http://URL/tableNo?id=99"``
## Response
```JSON
{
   "orderNum":123,
   "timestamp":
   "2020-01-21T07:44:45-05:00",
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
