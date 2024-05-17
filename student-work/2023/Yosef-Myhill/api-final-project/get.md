# API Reference- GET Method

## Overview

General Putnam's Motel Diner API processes a customer's meal order and retrieves the bill for the customer. The GET method is used to get the bill for the customer's order.

### Base URL

```
https://api.gpmd.com
```

### Authentication

Authentication and authorization are required before any request using the API. Supported authentication methods include:
* OAuth 2.0
* 2-factor Authorization
  
### HTTP Status Codes

The General Putnam Motel Diner API follows the standard HTTP status codes for success or failure of an API call.

<table>
	<tr>
		<th>Status Code</th>
		<th>Message</th>
    <th>Description</th>
	</tr>
  <tr>
    <td><code>100 - Continue</code></td>
    <td>Continue</td>
    <td>The system is waiting for further information to be added.</td>
  </tr>
	<tr>
		<td><code>200 - OK</code></td>
    <td>Success</td>
		<td>Request was successfully submitted.</td>
  </tr>
	<tr>
		<td><code>400 - Bad Request</code></td>
    <td>Invalid request</td>
		<td>The system cannot process the request. Review the request and correct any errors.</td>
	</tr>
  <tr>
		<td><code>401 - Unauthorized</code></td>
    <td>Authorization Failure</td>
		<td>Authorization attempt failed. Try again. </td>
	</tr>
 <tr>
   <td><code>500 - Internal Server Error</code></td>
   <td>Server Error</td>
   <td> Contact server support</td>
 </tr>
</table>

## GET/tableNo

A GET request is sent to retrieve the customer's bill from the system. The app finds the bill by using the customer's table number.

### Syntax

The following is the syntax for a GET request:

```
curl -X GET "http://URL/tableNo?id=customersTableNumber"
```

Insert the customer's table number as an integer between 1 and 16 in the customerTableNumber endpoint. For a takeout order, insert 99.

### Example

Here is an example of a GET call for a takeout order:
```
curl -X GET "http://URL/tableNo?id=99"
```
## Response

In the response to the GET call, the server sends an itemized bill of the customer's order.

### Syntax

The following is the syntax for the GET response:

``` JSON
{
   "orderNum":99,  
   "timestamp":"YYYY-MM-DDTHH:MM:SSTime Zone",  
   "ItemX":{  
  	"ItemOrdered":{  
     	"type":"Item Type",  
     	"Cost":12.95
  	}  
   } 
}
```
### Description

The following table contains the required parameters for the GET response.

<table> 
  <tr><th> Property Name</th>
    <th>Description</th>
    <th>Data Type</th>
  </tr>
  <tr>
    <td>orderNum</td>
    <td>A number to track the customer's order in the system. Can be an integer between 100 and 9999.</td>
    <td>integer</td>
  </tr>
  <tr>
    <td>timestamp</td>
    <td> A timestamp that displays the time and date of the GET response. The format for the timestamp is:
    <ul>
      <li>YYYY: Year</li>
      <li>MM: Month</li>
      <li>DD: Day</li>
      <li>T: Represents the switch from date to time</li>
      <li>HH: Hour (on a 24-hour clock)</li>
      <li>MM: Minute</li>
      <li>SS: Second</li>
      <li>timeZone: The local time zone (based upon UTC, follows the format HH:MM)</li>
    </ul>
    </td>
    <td>date</td></tr>
    <tr>
    <td>ItemX</td>
    <td>The number of an item in the customer's order (such as Item1 or Item2). The "ItemOrdered", "type", and "Cost" objects are children of "Item X". </td>
    <td>JSON object</td>
  </tr>
  <tr>
    <td>ItemOrdered</td>
    <td>Information about the item in the customer's order. The "type", and "Cost" objects are children of "ItemOrdered".</td>
    <td>nested JSON object</td>
  </tr>
  <tr>
    <td>type</td>
    <td>The type of item ordered by the customer. The value of the "type" object in the GET response corresponds to the value of the "mealCat" object in the POST request.</td>
    <td>string</td>
  </tr>
  <tr>
    <td>Cost</td>
    <td>The cost of the item in the customer's order.</td>
    <td>float</td>
  </tr>
</table>

### Example

Here is an example of a GET response for an order with:
* an order number of "123"
* a time stamp of January 21, 2020 at 07:44:45 UTC -05:00
* one burger meal that costs $10.99
* one salad that costs $9.50
  
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
