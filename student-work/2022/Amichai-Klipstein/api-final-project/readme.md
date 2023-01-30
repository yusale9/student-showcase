# Lunch API: Ordering a Burger
Lunch API is an application for ordering lunch through an application. We will go over ordering a burger meal.   
Ordering a burger includes two requests: POST and GET. Use the POST request for creating the order and the GET request for gathering data for the bill.
- [POST request](post.md)
- [GET request](get.md)  

 
This flowchart represents the procedure of ordering a burger at the diner:

```mermaid
  flowchart TD;
      A(start)-->B[select new order];
      B-->C[select burger meal];
      C-->D[choose patty, level of cooking, bun, condiments, toppings and specials]; 
      D-->E[choose first dish type and size];
      E-->F{do you want a second side dish?};
      F--Yes-->G[choose a second dish type and size];
      F--No-->H[select drink type and size];
      G-->H;
      H-->I{Ice?};
      I--Yes-->J[/confirm item/];
      I--No-->J;
      J-->K[/application adds table number, time and date stamp\];
      K-->L[/application adds price of the item\];
      J-->M{do you want add anything else?};
      M--Yes-->C;
      M--No-->N[/confirm order/];
      L-->M;
      N-->O[pay bill];
      O-->P[eat burger];
      P-->Q(end);
      
```
## Credits:
- Credits to [Alex Fiedler](linkedin.com/in/alexfiedler) for [this exercise](https://docs.google.com/document/d/11uNd8m5EorsLjGV84CjiJehiM8PxT2pdNbDFOnP3cDI/edit#).
- Credits to the [Good Docs Project](https://thegooddocsproject.dev/) for the [reference template](https://github.com/thegooddocsproject/templates/edit/master/api-reference/api-reference.md).
