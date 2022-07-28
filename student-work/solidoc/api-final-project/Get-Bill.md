# Get Bill Documentation

## GET/tableNo

This Get request is used to get the bill and includes the table number. 
The order number is included in the response. Take out orders are table 99. 
When this is printed, the customer can pay the bill. 

### Elements

Elements of the GET Request:

| Name      	| Data Type 	| Description                                        	|
|------------	|-----------	|---------------------------------------------------	|
| orderNum   	| Int         |Takeout order number                                 |
| tableNo   	| Int         | Table number for takeout orders                     |
| orderNum   	| Int         | Indicates what the specific order number is.        |
| timestamp  	| Timestamp 	| Date and time of order.                             |
| item        | String    	| Item in order                                       |
| type        | String      | Meal type                                           |
| cost        | Float       | Cost of item                                        |                                                                  


### Request

```none
HTTP curl -X GET "http://URL/tableNo?id=99"
```

### Response

```json
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


