# Lunch API: Ordering a Burger
Lunch API is an application for ordering lunch through an application. We will go over ordering a burger meal.   
Ordering a burger includes two requests: POST and GET. Use the POST request for creating the order and the GET request for gathering data for the bill.
- [POST request](post.md)
- [GET request](get.md)  

 
This flowchart represents the procedure of ordering a burger at the diner:

```mermaid
  flowchart TD;
      A(start)-->B[Select new order];
      B-->C[Select your meal];
      C-->D[Choose patty, level of cooking, bun, condiments, toppings and specials]; 
      D-->E[Choose first side dish type and size];
      E-->F{Do you want a second side dish?};
      F--Yes-->G[Choose a second dish type and size];
      F--No-->H[Select drink type and size];
      G-->H;
      H-->I{Do you want ice?};
      I--Yes-->J[Add ice];
      J-->K;
      I--No-->K[/Add table number, time and date stamp to order/];
      K-->L[/Adds price of the items to the order/];
      L-->M{Do you want add anything else?};
      M--Yes-->C;
      M--No-->N[/Confirm order/];
      N-->O[pay bill];
      O-->P[eat burger];
      P-->Q(end);
      
```
## Credits:
- Credits to [Alex Fiedler](linkedin.com/in/alexfiedler) for [this exercise](https://docs.google.com/document/d/11uNd8m5EorsLjGV84CjiJehiM8PxT2pdNbDFOnP3cDI/edit#).
- Credits to the [Good Docs Project](https://thegooddocsproject.dev/) for the [reference template](https://github.com/thegooddocsproject/templates/edit/master/api-reference/api-reference.md).
