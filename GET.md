## GET Documentation  

# GET/tableNo  
This request is sent when the client asks to receive the bill.  
GET reqest includes the table number. Order number is included in the GET response. Takeout orders are table 99.  


# Endpoint name

Method | syntax
----- | ----------
GET | base_url/endpoint/etc.

# GET Request  
NAME  | Type  | Description  
----- | ----| -----  
OrderNum  | string | Number exclusive for ordering the meal. The table number or takeouts.
timestamp | timestamp | The time the meal was ordered.
Item1 | string | First item ordered
ItemOrdered | string | The order requested by the client
type | string | Type of meal ordered
Cost | Float | Cost of the meal
Item2 | string | Second item ordered



# GET Request Curl  
  
curl -X GET "http://URL/tableNo?id=99"

# GET Response (JSON Object)  
``` JSON
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
