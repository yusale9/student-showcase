# Creating an API
## General Putnum Motel Diner API
This API is for customers of General Putnum Motel Diner to order online.
There is a GET.md for bills. There is a POST.md file for orders to the kitchen. I thank the Good Docs Project for their template. Also to Alex Fielder for their API document.  
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
S-->V
T-->V
U-->V
V{{Do you want a side?}}
V--Yes-->X
V--No-->AH
X[What side do I want?]
X-->Z
X-->AA
X-->AB
Z[Fries]
AA[Curly fries]
AB[Sweet potato fries]
AB-->AC
AC{{Do I want a drink?}}
AC--Yes-->AD
AC--No-->AH
AD[What drink do I want?]
AD-->AE
AD-->AF
AD-->AG
AE[Cola]
AF[Lemonade]
AG[Root beer]
AF-->AH
AH[Pay]
```
