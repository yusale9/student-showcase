# Order Meal

Method | syntax
----- | ----------
POST | /order


## Description

Creates an order and associates it with a table. See the [menu items list](menu-items.md) for the menu items you can order with this endpoint.

### Parameters
Name | type | Req. | Description
---- | ----- | ----- | --------------------
menuType | string | Y |  The menu used for the order. <br>Options: `"breakfast"`,`"lunch"`, `"dinner"`
tableNumber | int  | Y | The table to associated with the order. Takeaway orders are table `99`.
menuItems | Array\<meal\>| Y | An array of the `meal` objects included in the order. 

### Response

#### Response Arguments

Responses to successful requests include the following in the response body.

Name | type | Description
---- | ---- | ----------
orderNumber | int | The order number associated with a newly created order.

#### Response Codes
Code | Meaning
-----| -------
200  | OK: The order request succeeded. The response body contains the order number associated with the order.
400  | Bad Request: The order request isn't formatted properly.
500  | Error: Internal server error


## Examples

### Request

Sample request for a burger meal using cURL:

```BASH
curl -XPOST -H "Content-type: application/json" -d '{
    
    "menuType": "lunch",
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

Sample response object:

```JSON
{
  "orderNumber" : 123
}

```
