# POST/mealType
The JSON code documents the request being sent to the kitchen.  Once the request is completed, the order is printed in the kitchen for the chef to begin cooking.
For POC purposes, the burder meal is being documented.
More items will be expanded in the future.

## Code Guide

Name | type | Req. | Description
---- | ----- | ----- | --------------------
mealType | string | Y |  The type of meal being ordered, such as ``mealType``:``lunch.``
mealCat | string  | Y | Categorizes the meal being ordered.
main | string  | Y | The main course for the meal. Example for POC is ``burgerMeal.`` 
burger | string  | Y | Burger type that is ordered. 
pattyType | string  | Y | Type of patty being ordered. Example for POC is ``beef.``
pattyQty | string/int  | Y | Amount of patties ordered. For this example, only 1 is ordered.
pattyWeightG | string/int  | Y | Weight of the patty, such as 300grams.
pattyCook | string  | Y | Describes how the customer wants their burger to be cooked, such as ``MR`` for medium rare.
bunType | string  | Y | The type of bun ordered, such as ``wholeWheat,`` or ``white.``
condiment1 | string  | Y | 1st condiment being ordered, such as ``ketchup,`` ``secretSauce,`` ``thousand island dressing,`` ``mustard,`` ``BBQsauce.`` If no condiment is ordered, then ``None`` is selected.
condiment2| string  | Y | Same options as condiment1. If no condiment is ordered, then ``None`` is selected.
topping1 | string  | Y | First topping being ordered. Options include ``lettuce,`` ``tomatoes,`` and ``onions,``  If no topping is ordered, then ``None`` is selected. 
topping2| string  | Y | Second topping being ordered, same options as topping1. If no topping is ordered, then ``None`` is selected.
topping3 | string  | Y | Third topping being ordered, same options as topping1.  If no topping is ordered, then ``None`` is selected.
topping4 | string  | Y | Fourth topping being ordered, same options as topping1.  If no topping is ordered, then ``None``is selected.
side1 | string/int  | Y | First side being ordered, such as ``frenchFries.`` If a side is not ordered, then ``side1``:``one`` will be inputed.
side2 | string/int  | Y | Second side being ordered.  If a second side is not ordered, then ``side2``:``none`` will be inputed.
drink | string | Y | Type of drink being ordered, such as ``Coke,`` ``DietCoke``, ``Rootbeer``, ``Dr. Pepper``, or  ``Water``. 
size| string | Y | Size of drink being ordered, such as ``small``, ``medium``, ``large``, and ``extraLarge``. 
ice | boolean| Y | Indicates whether or not customer wants ice for their drink. Answer is either ``yes`` or ``no.``  
         

## Code Samples
```JSON
{
   "mealType":"lunch":[
   "mealCat" :{
      "main":"burgerMeal",
      "burger" :{
         "pattyType":"beef",
         "pattyQty":1,
         "pattyWeightG":300,
         "pattyCook":"MR",
         "bunType":"wholeWheat",
         "condiment1":"ketchup",
         "condiment2":"secretSauce",
         "topping1":"lettuce",
         "topping2":"pickles",
         "topping3":"None",
         "topping4":"None",
      },
      "sides":{ 
         "side1":{ 
            "type":"frenchFries",
            "size":"large"
         },
         "side2":{
            "type":"none",
            "size":""
         }
      },
      "drink":{
         "type":"Coke",
         "size":"large",
         "ice":true
      }
   }

```

# POST Response Example
```none
   200 OK
```
