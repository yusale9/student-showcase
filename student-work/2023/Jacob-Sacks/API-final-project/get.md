# GET /tableNo

## Overview

This HTTP request retrieves the bill for a specified table. The response is sent to the server to be brought the customer. The request takes the table number and outputs an itemized bill. For more information about the API in general, see the [readme file](readme.md).

## URL
```
https://api.gpmd.com/tableNo?id=<NUMBER>
```

Where \<NUMBER> is the customer's table number
For takeout orders the table number is 99.
## Request body parameter

The GET request has one parameter:

| Property | Description  | Data type | Possible values | Default | Required? |
|----------|--------------|-----------|-----------------|---------|-----------|
| tableNo  | Table number | integer   | 1-30            | 1       | Y         |

## Response parameters

Here is a table showing the different response parameters:

| Field       | Data Type   | Description                                        |
|-------------|-------------|----------------------------------------------------|
| orderNo    | Integer     | Order number for the bill                          |
| timestamp   | Date        | Time order was placed                              |
| item        | JSON object | Numbered list of items ordered                                       |
| itemOrdered | JSON object | Details of item                                    |
| type        | String      | Type of meal<br>(for POC, there's only burgerMeal) |
| cost        | Float       | Cost of item                                       |

## Example request

This would be the request for the bill for table number 18:

``` none
curl -X GET "http://URL/tableNo?id=18"
```

## Example response

```
{
   "orderNo":314,
   "timestamp":"2024-01-15T19:48:27-05:00",
   "Item1":{
  	"ItemOrdered":{
     	"type":"burgerMeal",
     	"Cost":21.50
  	}
   },
   "Item2":{
  	"ItemOrdered":{
     	"type":"burgerMeal",
     	"Cost":7.50
  	}
   }
}
```

## HTTP status codes

Here are the possible HTTP responses:

| Status code | Description    | Description                                            |
|-------------|----------------|--------------------------------------------------------|
| 200         | Success        | Bill was successfully printed |
| 400         | Invalid order  | Improper input, such as invalid table number            |
| 500         | Server problem | API couldn't connect to the server                     |

<br>
<br>

> This API documentation is adapted from a template provided by <a href="https://thegooddocsproject.dev/">The Good Docs Project</a>. This project is based on an exercise created by <a href="https://www.linkedin.com/feed/update/urn:li:activity:6626465471241732096/">Alex Feidler</a>.
