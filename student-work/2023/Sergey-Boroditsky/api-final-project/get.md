# GET /meal/burgerMeal

### Description:
Utilize the GPMD APIs to interact with the program's functionalities, such as placing orders and requesting bills. The GET method is utilized for initiating a bill request, while the POST method is used for creating a meal request. For further details about this API, refer to the README file.
### HTTP Method:
GET
### Parameters:
- tableNo: the number assigned to the table. For takeaway orders, the table number is 99.
- password: valid password for autentication
### Request Schema:
| Property | Description | Data Type |
|---|---|---|
| tableNo | Table number | int |
| password | Valid password | string |
### Request Example (cURL):
```
curl -X GET "https://meal/burgerMeal?tableNo=5&password=your_password"
```
### Response Codes:
| **Code** | **Status** | **Description** |
|---|---|---|
| 200 | OK | Request successfully processed |
| 305 | Wrong parameter | Invalid table number. Check tableNo. |
| 401 | Unauthorized | Invalid credentials. Check password. |
| 501 | General error | Something else went wrong. Generic error. |

### Response Scheme:
The response is a JSON object with a separate entry for each menu item that was ordered. Each menu item is represented by an 'ItemOrdered' object. The overall bill is calculated by summing up the prices of all the items in the order. Optional items in the response are omitted if not applicable.

| Property | Description | Data Type |
|---|---|---|
| orderNum | Order number | number |
| timeStamp | Time stamp of the response | string |
| Item1 | Ordered item No 1 | object |
| Item2 | Ordered item No 2. Optional | object |
| Item3 | Ordered item No 3. Optional | object |
| Item4 | Ordered item No 4. Optional | object |
| Item5 | Ordered item No 5. Optional | object |
| Item6 | Ordered item No 6. Optional | object |

### ItemOrdered object:
| **Property** | **Description** | **Data Type** |
|---|---|---|
| type | The menu item that was ordered | string |
| cost | The cost of the menu item | float |

### Response Example (JSON object):
```json
{
   "orderNum":103,
   "timestamp":"2023-07-15T08:45:30",
   "Item1":{
  	"ItemOrdered":{
     	"type":"salad",
     	"cost":7.99
  	}
   },
   "Item2":{
  	"ItemOrdered":{
     	"type":"drink",
     	"Cost":5.75
  	}
   }
}
```
