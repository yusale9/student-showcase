# Lunch API: Ordering a Burger
Lunch API is an application for ordering lunch through an application. We will go over ordering a burger meal.   
Ordering a burger includes two requests: POST and GET. Use the POST request for creating the order and the GET request for gathering data for the bill.  
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
      I--Yes-->J[/confirm order/];
      I--No-->J;
      J-->K[/add table number, time and date stamp\];
      K-->L[/add price of the item\];
      J-->M{do you want add anything else?};
      M--Yes-->C;
      M--No-->N[pay bill];
      L-->N;
      N-->O(end);
      
```
