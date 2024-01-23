# General Putnam Motel Diner

The General Putnam Motel Diner allows you to order for meals through ther app.

```mermaid
   flowchart TD
   A((Start Order))-->B[Select Bread type]
   B-->C[Select Patty]
   C-->D[Select burger size]
   D-->E[Select cook level]
   E-->F{want topping}
   F--Yes-->G[choose topping]
   F--No-->H{want condiments}
   G-->H{want condiments}
   H--Yes-->I[choose condiments]
   H--No-->J{want sides}
   I-->J{want sides}
  
