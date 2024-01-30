POST Meal
This is sent to the Kitchen. After an OK response is received, the client's order is printed in the kitchen, so the cook can begin cooking.  
This consists of a POST Request and POST Response

POST Request (JSON object)


POST Response  
Name Description Default Value Data Type Required  
Patty type Choice of the patty from Beef, chicken, lamb and vegan Beef  string  yes  
Burger size Weight of the Burger from 160g, 220g and 300gm 220g Integer yes
Bread type Type of bread from White, whole wheat, multigrain or gluten free white string yes
Cook level how much the patty needs to be cooked from medium, rate or well done well done string no
Condiments what condiments the client would like from ketchup, mustard, Mayonnaise, barbeque sauce and hot sauce string no
Toppings whether the client would like a topping on his burger from fried onions, fried mushrooms, fried egg or none string no
Sides which sides would the client like from a list of french fries, onion rings, salad, green beans, none string no
Side Size The size of the side dish from medium, large and extra large medium string no
Drinks choice of the drink the client would like with his meal from cola regular or zero, sprite, fanta, water, iced tea, soda, apple juice and grape juice cola regular string, yes
Drink size which size would the client like for his drink that is from the fountain and not a bottled drink. To choose from medium, large or extra large. medium, string no
ice in drink the person can request for ice or no ice in his drink True boolean and no
Extras if the client would like an extra side dish from fried cauliflower, sweet potato chips, chicken wings or chicken nuggets none string no
