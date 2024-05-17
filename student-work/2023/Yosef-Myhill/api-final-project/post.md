# API Reference- POST Method

## Overview

General Putnam's Motel Diner API processes a customer's meal order and retrieves the bill for the customer. The POST method is used to order a meal from the menu. 

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

##  POST Request for "burgerMeal"

"mealCat" value of "burgerMeal". The "burgerMeal" API call allows the user to choose a meal that includes a burger, 1 or 2 side dishes, and a soft drink.

### Syntax

The "burgerMeal" endpoint is nested under the "lunch" value in the "mealType" object.

```
curl -H "Content-Type: application/json" -X POST -d'
{
	"mealType": "lunch",
	"mealCat": "burgerMeal"
}
```

### POST/lunch/burgerMeal/burger

The "burger" endpoint is used to order the burger patty, bun, and toppings.
   
#### Description

The following table contains the parameters for the "burger" endpoint.

<table> 
  <tr>
    <th> Property Name</th>
    <th>Description</th>
    <th>Default Value</th>
    <th>Data Type</th>
    <th>Mandatory/Optional</th>
  </tr>
  <tr>
    <td>pattyType</td>
    <td>Specifies the type of burger. Can be:
      <ul>
      <li>"beef"</li>
      <li>"chicken"</li>
      <li>"veggie"</li>
    </ul></td>
    <td>"beef"</td>
    <td>string</td>
    <td>Mandatory</td>
  </tr>
  <tr>
    <td>pattyQty</td>
    <td>The number of patties to prepare. Accepatable values are 1-4.</td>
    <td>1</td>
    <td>int</td>
    <td>Mandatory</td>
  </tr>
  <tr>
    <td>pattyWeightG</td>
    <td>Specifies the weight of the patty in grams. Acceptable values are:
      <ul>
        <li>200</li>
        <li>250</li>
        <li>300</li>
        <li>400</li></ul></td>
    <td>250</td>
    <td>int</td>
    <td>Mandatory</td>
  </tr>
  <tr>
    <td>pattyCook</td>
    <td>How well the patty should be cooked. Can be:
     <ul>
        <li>"R" (rare)</li>
        <li>"MR" (medium rare)</li>
        <li>"M" (medium)</li>
        <li>"MW" (medium well)</li>
        <li>"W" (well-done)</li></ul>
      </td>
      <td>"M"</td>
      <td>string</td>
      <td>Mandatory</td></tr>
      <tr>
        <td>bunType</td>
        <td>Specifies the type of bun used for the burger. Can be:
        <ul>
          <li>"white" (plain white bun)</li>
          <li>"sesame" (white bun with sesame seeds)</li>
          <li>"wholeWheat" (whole wheat bun)</li>
          <li>"glutenFree" (gluten-free bun)</li></ul>
        </td>
        <td>"white"</td>
        <td>string</td>
        <td>Mandatory</td>
      </tr>
      <tr>
        <td>condiment1</td>
        <td>Specifies the first condiment to put on the burger. Can be:
        <ul>
          <li>"ketchup"</li>
          <li>"mustard"</li>
          <li>"relish"</li>
          <li>"none"</li>
        </ul>
        </td>
        <td>"ketchup"</td>
        <td>string</td>
        <td>Optional</td>
      </tr>
      <tr>
        <td>condiment2</td>
        <td>Specifies the second condiment to put on the burger. Can be:
        <ul>
          <li>"secretSauce" (General Putnam's secret sauce)</li>
          <li>"periPeri" (peri-peri sauce)</li>
          <li>"bbq" (barbecue sauce)</li>
          <li>"none"</li>
        </td>
        <td>"secretSauce"</td>
        <td>string</td>
        <td>Optional</td>
      </tr>
          <tr>
        <td>topping1</td>
        <td>Specifies the first topping to put on the burger. Can be:
        <ul>
          <li>"lettuce"</li>
          <li>"tomato"</li>
          <li>"cucumber"</li>
          <li>"none"</li>
        </ul>
        </td>
        <td>"lettuce"</td>
        <td>string</td>
        <td>Optional</td>
      </tr>
      <tr>
        <td>topping2</td>
        <td>Specifies the second topping to put on the burger. Can be:
        <ul>
          <li>"pickles"</li>
          <li>"hotPeppers" (hot peppers)</li>
          <li>"olives"</li>
          <li>"none"</li>
        </td>
        <td>"pickles"</td>
        <td>string</td>
        <td>Optional</td>
      </tr>
          <tr>
        <td>topping3</td>
        <td>Specifies the third topping to put on the burger. Can be:
        <ul>
          <li>"onion"</li>
          <li>"friedOnion" (fried onions)</li>
          <li>"cheese"</li>
          <li>"none"</li>
        </td>
        <td>"onion"</td>
        <td>string</td>
        <td>Optional</td>
      </tr>
</table>

#### Example

Here is an example of a POST call for a burger that includes:
* one 300 gram beef patty cooked to Medium-Rare
* a whole wheat bun
* ketchup
* General Putnam's secret sauce
* lettuce
* pickles
* onion

```json
"burger": {
		"pattyType": "beef",
		"pattyQty": 1,
		"pattyWeightG": 300,
		"pattyCook": "MR",
		"bunType": "wholeWheat",
		"condiment1": "ketchup",
		"condiment2": "secretSauce",
		"topping1": "lettuce",
		"topping2": "pickles",
		"topping3": "onion"
	}
```
### POST/lunch/burgerMeal/burger/sides

The "sides" endpoint is used to order the side dishes served with the burger.
#### POST/lunch/burgerMeal/burger/sides/side1

The "sides1" endpoint is used to order the first side dish served with the burger.
##### Description    
The following table contains the parameters for the "sides1" endpoint.
<table>
  <tr>
    <th>Property Name</th>
    <th>Description</th>
    <th>Default Value</th>
    <th>Data Type</th>
    <th>Mandatory/Optional</th>
  </tr>
  <tr>
	<td>type</td>
	  <td>Specifies the type of side dish. Can be: 
	  <ul>
          <li>"frenchFries" (regular french fries)</li>
          <li>"spicyFries" (spicy french fries)</li>
          <li>"rice"</li>
	  </ul>
	</td>
	  <td>"french fries"</td>
	<td>string</td>
	<td>Mandatory</td>
  </tr>
<tr>
	<td>size</td>
	<td>Specifies the type of side dish. Acceptable values are "regular" and "large".</td>
	<td>"regular"</td>
	<td>string</td>
	<td>Mandatory</td>
</tr>
</table>

#### POST/lunch/burgerMeal/burger/sides/side2

The "sides2" endpoint is used to order the second side dish served with the burger.

##### Description

The following table contains the parameters for the "sides1" endpoint.
<table>
  <tr>
    <th>Property Name</th>
    <th>Description</th>
    <th>Default Value</th>
    <th>Data Type</th>
    <th>Mandatory/Optional</th>
  </tr>
  <tr>
	<td>type</td>
	  <td>Specifies the type of side dish. Can be: 
	  <ul>
          <li>"grits"</li>
          <li>"friedOkra" (breaded and fried okra)</li>
          <li>"potatoSalad" (potato salad)</li>
          <li>"none"</li>
	  </ul>
	</td>
	  <td>"none"</td>
	<td>string</td>
	<td>Optional</td>
  </tr>
<tr>
	<td>size</td>
	<td>Specifies the size of the side dish. Acceptable values are "regular", "large", and "" (none).</td>
	<td>"regular"</td>
	<td>string</td>
	<td>Optional</td>
</tr>
</table>

#### Example

Here is an example of a POST call for one large side dish of french fries:
```json
 "sides": {
		"side1": {
			"type": "frenchFries",
			"size": "large"
		},
		"side2": {
			"type": "none",
			"size": ""
		}
```
### Drink

The "drink" endpoint is used to order a soft drink.

#### Description    
The following table contains the parameters for the "drink" endpoint.

<table>
  <tr>
    <th>Property Name</th>
    <th>Description</th>
    <th>Default Value</th>
    <th>Data Type</th>
    <th>Mandatory/Optional</th>
  </tr>
  <tr>
	<td>type</td>
	  <td>Specifies the type of soft drink. Can be: 
	  <ul>
          <li>"coke" (Regular Coca Cola)</li>
          <li>"dietCoke" (Diet Coke-Regular)</li>
          <li>"sprite" (Sprite)</li>
          <li>"fanta" (Fanta orange soda)</li>
	  <li>"sweetTea" (Home-brewed sweet tea)</li>
	  <li>"water" (Dasani bottled water)</li>
	  <li>"none"</li>
	  </ul>
	</td>
	  <td>"coke"</td>
	<td>string</td>
	<td>Optional</td>
  </tr>
<tr>
	<td>size</td>
	<td>Specifies the size of the soft drink. Acceptable values are "regular", "large", and "" (none).</td>
	<td>"regular"</td>
	<td>string</td>
	<td>Optional</td>
</tr>
<tr>
	<td>ice</td>
	<td>Whether to put ice in the soft drink. Acceptable values are true and false.</td>
	<td>true</td>
	<td>boolean</td>
	<td>Mandatory</td>
</tr>
</table>

#### Example
Here is an example of a POST call for a large coke with ice:
```json
"drink": {
		"type": "coke",
		"size": "large",
		"ice": true
	}
```
## POST Response for "burgerMeal"

The API responds to the POST request with a standard HTTP status code. This code indicates if the API call was successful, and if not, what the error is.

### Description
The following table contains a list of status codes and what they mean.

<table>
	<tr>
		<th>Status Code</th>
		<th>Description</th>
	</tr>
	<tr>
		<td><code>200 - OK</code></td>
		<td>Your meal was successfully ordered.</td>
	<tr>
		<td><code>400 - Bad Request</code></td>
		<td>Your order was unacceptable. Most likely, this is due to unsupported additions to the meal request.</td>
	</tr>
  <tr>
		<td><code>401 - Unauthorized</code></td>
		<td>Your order was unacceptable. Most likely, this is due to unsupported additions to the meal request.</td>
	</tr>
	<tr> 
		<td><code>408 - Request Timeout</code></td>
		<td>The server would like to shut down the unused connection. Most likely, the customer fell asleep while making the order and needs to be gently woken up.</td>
	</tr>
</table>

### Example

```http
200 OK
```
