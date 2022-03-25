# GET Reference Guide
The order given to the server. Includes the table and order number.  

## Code Guide

Name | type | Req. | Description
---- | ----- | ----- | --------------------
Item1 | string | Y |  Describes the customer's order
Item2 | int  | N | Provides customer's order number and time of order

## Code Samples
```JSON
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


