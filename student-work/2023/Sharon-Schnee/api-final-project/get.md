# Request the bill

This GET call allows customers to request the bill following a meal order. When this is printed, the customer can pay the bill. 

Method | syntax
----- | ----------
GET | "http://api.gphd.net/tableNo?id=99

### Request Path Parameters

Name | type | Required | Description | Default 
---- | ----- | ----- | -------------------- | ---
Id | integer | Y |  The table number. Take out orders are table 99. |

## Examples

### Request

Include the authorization header using the following structure. For more information about Authentication, see the [ReadMe](https://github.com/Schnee18/student-showcase/blob/main/student-work/2023/Sharon-Schnee/api-final-project/readme.md) file.

```
curl --request GET https://api.gphd.net/tableNo?id=99
--header 'Content-Type: application/json'
--header 'Authorization: Bearer ImahFWLZWFdD8VVcUtIED2YuOjPFlZpldQTE5tUqKdv'
```

### Response

```
{
   "orderNum":123,
   "timestamp":"2020-01-21T07:44:45-05:00",
   "Item1":{
  	"ItemOrdered":{
     	"type":"burgerMeal",
     	"Cost":10.99
  	}
   },
}
```

### Response Parameters

Name | type | Description | Example 
---- | ----- | ----- | --------------------
OrderNum | integer | The order number. |  123
timestamp | date  | The time the bill was requested in ISO time date and time format. | 2020-01-21T07:44:45-05:00

Name | type | Description | Example 
---- | ----- | ----- | --------------------
Item | string | The item ordered object. | item1
ItemOrdered | The order array. | List item and cost of item in an order.
type | string |The type of item ordered. | burgerMeal
Cost | integer | The cost of the order. | 10.99

### Response status codes

| Status code |  Description          |
|-------------|----------------------|
| `100 - Initial request received` | That's a good start, let's keep going. |
| `200 - OK` | Request successful. Enjoy your meal. |
| `400 - Bad Request`       | Request failed. Check your request and try again. |
| `500 - Internal Server Error`  | Server error. Please contact the server administrator.  |
