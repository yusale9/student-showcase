# Hamburger API Doc
This is the reference for the Hamburger API, which is part of the new Hamburger app of General Putnam Motel Diner (GPMD). With the Hamburger app, GPMD customers can place take-out orders in a touchless manner. 

This preliminary version of the app lets customers order only take-out hamburger meals. If the app is successful, GPMD plans to expand the app to include other meals from the GPMD menu and put the app on a tablet so that patrons can order from their seats in the diner.
The Hamburger API is used to interface between the Hamburger app and the server-side ordering system in GPMD's kitchen, which prints out orders for the cooks. 

The API follows REST principles, uses JSON to encode requests and responses, and relies on standard HTTP codes to signal operation outcomes.

The Hamburger API currently contains the following methods:
* [GET](get.md) - retrieves data from the server. In this case, the GET for the POC will be to GET the bill.
* [POST](post.md) - sends data to the server. In this case, the POST will send the customer’s order to the server in the kitchen. The printer in the kitchen will print out the order for the cook to use.


## Workflow
The app uses the following workflow:

```mermaid
   flowchart TD;
   
   A([START]) --> B[Order burger];
   B-->C[/Choose your patty type/];
   C-->D[/Choose the number of patties you want/];
   D-->E[/Choose your bun type/];
   E-->F{Do you want a condiment?};
   F--Yes-->G[Order first condiment];
   G-->H{Do you want another condiment?};
   H--Yes-->I[Order second condiment];
   H--No-->J{Do you want a topping on your burger?};
   J--Yes-->K[Order first topping];
   I-->J
   F--No-->J
   K-->L{Do you want a second topping?};
   L--Yes-->M[Order second topping];
   M-->N{Do you want a third topping?};
   N--Yes-->O[Order third topping];
   O-->P{Do you want a side with your burger?};
   J--No-->P;
   P--Yes-->Q[Order first side];
   Q-->R{Do you want another side?};
   R--Yes-->S[Order second side];
   S-->T{Do you want a drink?};
   T--Yes-->U[Order drink];
   R--No-->T;
   P--No-->T;
   T--No-->V([End]);
   U-->V
```  

## Credits
The idea for this project and all code snippets came from Alex Fiedler's [General Putnam Motel Diner API Guide](https://www.linkedin.com/feed/update/urn:li:activity:6626465471241732096/).

The endpoint references of this API are based on the “The Good Docs” project template for [API Reference](https://github.com/thegooddocsproject/templates/blob/master/api-reference/api-reference.md). 
