# GET Command 
The GET call is used to request and generate the bill for a patron's order. It consists of two parts:  
* The GET request (JSON object)
* The GET response (JSON object)
 
## GET Request (JSON object)  
* The GET request is a URL with an endpoint specifying the tableNum, which is all that is needed to generate a bill in the response.
* When the patron is ready for the bill, the app requests the bill information from the server.

### Code Snippet for GET Request    
Take-out orders, by default, are set to appear as tableNo 99, to differentiate them from patrons dining in.  
```
JSON
curl -X GET "http://URL/tableNo?id=99"
```
### Code Snippet Explained  
The endpoint "99" at the end of the URL specifies the take-out bill request.

## GET Response (JSON Object)  
* The GET response consists of the orderNum, timestamp, items ordered, and cost.
* If the tableNum, 99 in this example, is correctly specified, the server will generate a bill.
* A printout will be given to the customer in order to pay.

### Code Snippet for GET Response  

```JSON
{
   "orderNum":123,
   "timestamp":"2020-01-21T07:44:45-05:00",
   "Item1":{
  	 	"type":"burgerMeal",
     	"Cost":10.99
  	},
     "Item2":{
  	"ItemOrdered":{
     	"type":"salad",
     	"Cost":9.50
  	}
   }
}
```
  
### Properties Table for GET Response Code Snippet  
The GET response consists of various properties.  These properties are listed below according to their objects. 
#### JSON Objects 1: **orderNum and timestamp**  

| Property Name | Value                       | Data Type | Mandatory | Description                                        | 
|---------------|-----------------------------|-----------|-----------|----------------------------------------------------|  
| orderNum      | 123                         | integer   | Y         | The number identifying a patron's order.           |  					
| timestamp	    | "2020-01-21T07:44:45-05:00" | string    | Y         | The date and time the order was submitted.         |  

#### JSON Object 2: **Item1**  

| Property Name | Value                   | Data Type | Mandatory | Description                                        | 
|---------------|-------------------------|-----------|-----------|----------------------------------------------------|  
| Item1         |                         | string    | Y         | First order item.                                  |  					
| type        	| "burgerMeal"            | string    | Y         | The type of meal ordered.                          |  
| Cost          | 10.99                   | float     | Y         | The cost of item1.                                 |  

#### JSON Object 3: **Item2**  

| Property Name | Value                   | Data Type | Mandatory | Description                                        | 
|---------------|-------------------------|-----------|-----------|----------------------------------------------------|  
| Item2         |                         | string    | Y         | Second order item.                                 |  					
| type        	| "salad"                 | string    | Y         | The type of meal ordered.                          |  
| Cost          | 9.50                    | float     | Y         | The cost of item2.                                 |  

 
 
