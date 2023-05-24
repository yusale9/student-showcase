## POST Order meal
Sends your meal order.
### Response schema

| Argument | Type    | Description                  |
|-----------|--------|------------------------------|
| meal_type     | string | The meal you ordered  |
| mealCat   | string | Type of meal ordered.               |
|           |        |                              |

### Response example

```
{Provide an example of the API response, filled with sample values.}
```
```
curl -H "Content-Type: application/json" -X POST -d'
{
	"mealType": "lunch",
	"mealCat": "burgerMeal",
	  "burger": {
		"PattySize":"M",
		"pattyQty": 1,
		"pattyWeightG": 200,
		"pattyCook": "MR",
		"BunType": "seeded",		
		"Fixing1": "lettuce",
		"Fixing2": "pickles",
		"Fixing3": "tomato"
	},
	"sides": {
		"side1": {
			"FriesType":"SweetPotaoFries",
			"size": "large"
		},
		"side2": {
			"type": "none",
			"size": ""
		}
	},


}

   }
