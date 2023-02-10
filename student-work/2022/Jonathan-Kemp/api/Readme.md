# Creating an API
## General Putnum Motel Diner API
An API is being created so that General Putnum Motel Diner can allow customers to order online.
In order for this API to work there has to be a place to see the menu. This is called the GET.md file, it acts as both a virtual table in the restaurant, and a menu to order from. There is also the POST.md file, this acts as a virtual waiter/waitress. It takes your order to the kitchen where it is printed out. Below is the flow chart for a customer ordering from the menu, the order being sent to the kitchen, and the bill being paid.
```mermaid
flowchart TD
A((Start))
A-->B
B{{Do I want a burger}}
B--Yes-->C
B--No-->D
D[Go and order something else]
C[What size burger?]
C-->E
C-->F
C-->G
E[160g]
F[200g]
G[300g]
F-->H
H[How do I want it cooked?]
H-->I
H-->J
H-->K
H-->L
I[Rare]
J[Medium rare]
K[Medium]
L[Well done]
J-->M
M[What bun do I want?]
M-->N
M-->O
M-->P
M-->Q
N[Regular]
O[Seeded]
P[Chiabatta]
Q[Gluten Free]
O-->R
R[What filling do I want?]
R-->S
R-->T
R-->U
S[Lettuce]
T[Tomato]
U[Pickle]
