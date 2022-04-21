# GET Reference Guide
The order given to the server. Includes the table and order number.  The server returns the order to the specified table number.  

## GET/ORDER Response

Name | type |  Description
---- | ----- | --------------------
Item1 | string | Describes the customer's order
Item2 | int | Second Order 
orderNum | int | Order Number 
timestamp | string/int | Time order was placed 
ItemOrdered | string | Item that was ordered 

## Code Samples
### GET Request
```HTTP

"curl -X GET "http://URL/tableNo?id=99"

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
}```
