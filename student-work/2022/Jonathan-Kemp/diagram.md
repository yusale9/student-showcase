# Ordering Lunch
A flowchart that shows the desicsions about ordering lunch.

```mermaid
flowchart TD
A((Start))
A-->B[I am hungry]
B-->C[Order lunch]
C-->D[Choose something]
D-->E[Milk]
D-->F[Meat]
E-->G[Soup]
E-->H[Salad]
E-->I[Sandwich]
F-->J[Soup]
F-->K[Steak]
F-->L[Burger]
G-->M[Choose a drink]
H-->M[Choose a drink]
I-->M[Choose a drink]
J-->M[Choose a drink]
K-->M[Choose a drink]
L-->M[Choose a drink]
M-->N[Hot]
M-->O[Cold]
N-->P[Pay]
O-->P[Pay]
P-->Q((Eat))
