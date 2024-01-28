# GET: Bill Documentation  

## GET Burger Value Meal Bill  

The GET request is sent when the waiter/waitress wants to get the bill.  The GET response is printed and given to the customer so they can pay the bill.   

## Sample JSON Code Snippet  

### Request Command URL  

```
curl -X GET "http://URL/tableNo?id=99"
```

### GET Bill Code  

```
{
"orderNum":123,
"timestamp":"2020-01-21T07:44:45-05:00",
"Item1":{
"ItemOrdered":{
"type":"burgerValueMeal",
"Cost":12.14
}
}
}
```

