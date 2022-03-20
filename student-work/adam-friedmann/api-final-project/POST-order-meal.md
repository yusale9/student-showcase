# Order Meal

Method | syntax
----- | ----------
POST | https://putnamapp.com/order


## Description

Creates a meal order and associates it with a table. See the [Menu Items Index](menu-items-index.md) for information on the menu items you can order with this endpoint.

### Parameters

Name | type | Req. | Description
---- | ----- | ----- | --------------------
mealType | string | Y |  The meal being ordered. <br>Options: `"breakfast"`,`"lunch"`, `"dinner"`
tableNumber | int  | Y | The table to associated with the order.
menuItems | Array\<menuItem\>| Y | An array of the `menuItem` objects included in the order. 

### Response

#### Response Codes

Code | Meaning
-----| -------
200  | OK: The order request succeeded. The response body contains the order number associated with the order.
404  | Not Found: Either the table number doesn't exist, or the requested table doesn't have an open order.
500  | Error: Internal server error




## Examples

### Request

Here is a sample request for a burger meal using cURL.

```BASH
curl -XPOST -H "Content-type: application/json" -d '{
    
    "mealType": "lunch",
    "tableNumber" : 12,
    "menuItems": [
        {
            "burgerMeal" : {
                "burger": {
                    "pattyType": "beef",
                    "pattyQuantity": 1,
                    "pattyWeight": 300,
                    "pattyCook": "mediumRare",
                    "bunType": "wholeWheat",
                    "condiments": [
                        "ketchup",
                        "secretSauce"
                    ],
                    "toppings": [
                        "lettuce",
                        "pickles"
                    ]
                },
                "sides": [
                    {
                        "type": "frenchFries",
                        "size": "large" 
                    }
                ],
                "drink": {
                    "type": "coke",
                    "size": "large",
                    "ice": true
                }
            }
        }
    ]
}' 'https://www.putnamapp.com/order'
```

### Response

```HTTP
<!--  A copy-and-paste working request, if possible. Not one with values replaced by their names, such as "ID." -->

```

<!-- Follow with comments to explain what each part of the request is doing -->

<!-- Write a comment explaining the response, if it would be helpful. For a response with a complicated schema, create a table like the one used above for the request.  -->

```JSON
{
    "mealType": "lunch",
    "tableNumber" : 12,
    "menuItems": [
        {
            "burgerMeal" : {
                "burger": {
                    "pattyType": "beef",
                    "pattyQuantity": 1,
                    "pattyWeight": 300,
                    "pattyCook": "mediumRare",
                    "bunType": "wholeWheat",
                    "condiments": [
                        "ketchup",
                        "secretSauce"
                    ],
                    "toppings": [
                        "lettuce",
                        "pickles"
                    ]
                },
                "sides": [
                    {
                        "type": "frenchFries",
                        "size": "large" 
                    },
                    {
                        "type": "none", //No need for this.
                        "size": ""
                    }
                ],
                "drink": {
                    "type": "coke",
                    "size": "large",
                    "ice": true
                }
            }
        }
    ]
}
```
