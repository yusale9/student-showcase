# Menu Items Index

This index contains a list of all the items on the Putnam Diner menu that you can order using the app. Each menu item is represented in the app by a meal
object that contains several smaller meal component objects. Meal objects define which components are included in a meal, as well the limits of the numbers
and sizes of the meal components.

>Note
>
>The POC version of the app only supports the `burgerMeal` meal object.

## Meal Objects

These are the meal objects that you can use when [placing orders]() with the app.

### burger
An object representing a burger. `burger` items contain the following properties:

Name | type | Req. | Description
-----| -----| ---- | -----------
pattyType | string | Y | The type of patty in the burger. <br>Options: `"beef"`, `"chicken"`, `"veggie"`
pattyWeight | int | Y | The weight of the patty, in grams. <br>Options: `100`, `200`, `300`
pattyCook | string | Y | How cooked the patty is. <br>Options: `"rare"`, `"mediumRare"`, `"wellDone"`
pattyQuantity | int | Y | The number of patties in the burger. The maximum value is `3`. The values for `pattyType`, `pattyWeight`, and `pattyCook` are the same for all patties.
bunType | string | Y | The type of bun for the burger. <br>Options: `"white"`, `"wholeWheat"`, `"glutenFree"`
condiments | Array\<string\> | N | The condiments for the burger. You can only add 2 condiments to a burger. If the `condiments` array includes more than 2 items, only the first 2 are included in the order. <br>Options: `"ketchup"`, `"mustard"`, `"chimichurri"`, `"mayo"`
toppings | Array\<string\> | N | The toppings for the burger. You can only add 3 toppings to a burger. If the `toppings` array includes more than 3 items, only the first 3 are included in the order. <br>Options: `"lettuce"`, `"pickles"`, `"tomatoes"`, `"friedEgg"`
