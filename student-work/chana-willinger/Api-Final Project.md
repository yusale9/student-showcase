## GET/tableNo

This is the call sent when the patron wants to get their bill. The GET request includes the table number. Take out orders are table 99. When this is printed, the customer can pay the bill.

## Code Example

```curl
      curl -X GET "http://URL/tableNo?id=99"


## Response Example 

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
   };
```

These are the items included.

| orderNum    | int         | The order number              |
|-------------|--------     |-------------------------------|
| timestamp   | timestamp   | The time the order was placed |
| Item1       | string      | Describes the order placed    |
| ItemOrdered | string      | Descibes the type of meal     |
| type        | string      | Food type                     |
| cost        | float       | Cost of food item             |
| Item2       | string      | Second food order placed      |




