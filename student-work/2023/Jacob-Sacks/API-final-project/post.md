# POST dinner/burgerMeal

## Overview

This HTTP request creates an order for the kitchen to make based on a customer's order. As a POC, the API can only take dinner orders for a burger meal. In the future, the API will be able to handle all kinds of meals throughout the day. For more information about the API in general, see the [readme file](readme.md).

## URL
```
https://api.gpmd.com/dinner/burgerMeal
```

## Parameters

The order is a JSON object containing the details of the burger, the side(s), and the drink.

### Burger properties

Here is a table showing the different burger properties:

| Property    | Description             | Data type | Possible values                                                                              | Default     | Required? |
|-------------|-------------------------|-----------|----------------------------------------------------------------------------------------------|-------------|-----------|
| pattyType   | Type of meat for burger | string    | Beef, Lamb, Chicken, Vegan                                                                   | Beef        | Y         |
| pattyCook   | Burger doneness         | string    | Rare, Medium rare, Medium, Medium well, Well done                                            | Medium      | Y         |
| pattyWeight | Patty weight            | integer   | 160, 250, 300                                                                                | 160         | Y         |
| pattyQty    | Number of patties       | integer   | 1, 2, 3                                                                                      | 1           | Y         |
| bunType     | Bread type for bun   | string    | White bread, Rye, Whole wheat, gluten-free                                                   | White bread | Y         |
| topping1    | First burger topping    | string    | Lettuce, Tomato, Fried onions, Red onions, Pickles, Jalapenos, Vegan cheese, Fried egg, none | none        | N         |
| topping2    | Second burger topping   | string    | Lettuce, Tomato, Fried onions, Red onions, Pickles, Jalapenos, Vegan cheese, Fried egg, none | none        | N         |
| topping3    | Third burger topping    | string    | Lettuce, Tomato, Fried onions, Red onions, Pickles, Jalapenos, Vegan cheese, Fried egg, none | none        | N         |
| condiment1  | First condiment         | string    | Ketchup, Mustard, Garlic mayo, Thousand island, BBQ sauce, Mayonnaise, none                  | none        | N         |
| condiment2  | Second condiment        | string    | Ketchup, Mustard, Garlic mayo, Thousand island, BBQ sauce, Mayonnaise, none                  | none        | N         |
| condiment3  | Third condiment         | string    | Ketchup, Mustard, Garlic mayo, Thousand island, BBQ sauce, Mayonnaise, none                  | none        | N         |

### Side properties

Each side is its own object with its own properties. The customer is limited to 2 sides. Here is a table showing the different properties each side has:

| Property | Description  | Data type | Possible values                                                                                     | Default | Required? |
|----------|--------------|-----------|-----------------------------------------------------------------------------------------------------|---------|-----------|
| type     | Type of side | string    | Fries, Rice, Mashed potatoes, Onion rings,<br>Sweet potato fries, Garden salad, Israeli salad, none | none    | N         |
| size     | Size of side | string    | Small, Medium, Large, none                                                                          | none    | N         |

### Drink properties

Here is a table showing the different drink properties:

| Property | Description   | Data type | Possible values                                                            | Default | Required? |
|----------|---------------|-----------|----------------------------------------------------------------------------|---------|-----------|
| type     | Type of drink | string    | Coke, Coke zero, Sprite, Sprite zero,<br>Lemonade, Iced tea, Seltzer, none | none    | N         |
| size     | Size of drink | string    | Small, Medium, Large, none                                                 | none  | N         |
| ice      | Ice in drink  | boolean   | true or false                                                              | true    | N         |

## HTTP status codes

| Status code | Description    | Description                                            |
|-------------|----------------|--------------------------------------------------------|
| 200         | Success        | Meal was successfully received and sent to the kitchen |
| 400         | Invalid order  | Improper input, such as too many toppings              |
| 500         | Server problem | API couldn't connect to the server                     |
