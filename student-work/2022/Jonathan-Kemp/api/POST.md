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
		"pattyType": "beef",
		"pattyQty": 1,
		"pattyWeightG": 200,
		"pattyCook": "MR",
		"bunType": "seeded",		
		"topping1": "lettuce",
		"topping2": "pickles",
		"topping3": "tomato"
	},
	"sides": {
		"side1": {
			"type": "sweetPotatoFries",
			"size": "large"
		},
		"side2": {
			"type": "none",
			"size": ""
		}
	},
	"drink": {
		"type": "Lemonade",
		"size": "large",
		"ice": true
    }

}

   }
