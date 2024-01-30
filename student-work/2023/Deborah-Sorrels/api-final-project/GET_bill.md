# GET: Bill Documentation  

## GET Burger Value Meal Bill  

The GET request is sent when the waiter/waitress wants to get the bill.  The GET response is printed and given to the customer so they can pay the bill.   

## Sample JSON GET Request URL   

```
curl -X GET "http://URL/tableNo?id=99"
```

## Sampel GET JSON Response Code Snippet  

``` JSON 
{
"orderNum":123,
"timestamp":"2020-01-23T07:44:45-05:00",
"Item1":{
"ItemOrdered":{
"type":"burgerValueMeal",
"Cost":12.14
}
}
}
```

### Request Status Code

```
200 OK  
400 Bad Request  
500 Internal Server Error   
503 Service Unavailable
```

## Code Explanation

Property Name | Data Type | Description
------------- | --------- | -----------
orderNum | integer | A unique set of numbers that identify each order.  
timestamp | date | The time the meal was ordered.  
Item1 | N/A | Lists the specific number of items ordred.   
ItemOrdered | N/A | Lists the item ordered. 
type | string | Lists the specific item ordered.  
Cost | integer | Lists the amount of the bill.  







