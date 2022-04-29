## GET/tableNo

This is the call that is sent when the server wants to get the bill. 
The GET request includes the table number. 
The order number is included in the response. 
Take out orders are table 99. When this is printed, the customer can pay the bill.

### Response

```JSON

{
   "orderNum":123,
   "timestamp":"2022-03-29T07:44:45-05:00",
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

The following table depicts the elements of the response for GET/tableNo.

| Name      	| Data Type 	| Description                                                                                      	|
|------------	|-----------	|-------------------------------------------------------------------------------------------------	|
| orderNum   	| Int  | Indicates what the specific order number is.                                                      |
| timestamp  	| Timestamp 	| The timestamp shows the date and time the order was placed.                                       |
| item     | String    	| Indicates the item(s) ordered, beneath which can be seen what was ordered and the cost.           |
| type        | String      | Indicates what meal was specifically ordered.                                                     |
| cost        | Float       | Indicates the price of the item that was ordered.


