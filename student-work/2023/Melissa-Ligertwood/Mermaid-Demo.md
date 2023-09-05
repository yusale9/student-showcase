````mermaid
flowchart TD;
A([Start]) -->B[Wake Up];
B -->C[Get out of bed];
C -->D[Walk to bathroom];
D -->E[Brush teeth]
E -->F{Working from home?}
F --No-->G[Take shower]
F --Yes-->H[Wash face]
H -->I[Pour cup of coffee]
I -->J[Get laptop]
J ------->K[Start working]
K -->L([End])
G -->M[Get ready]
M -->N[Pack lunch]
N -->O[Drive to Starbucks]
O -->P[/Order Coffee/]
P -->Q[Drive to work]
Q -->R[/Pay for Parking/]
R -->S[Walk to office]
S --> K;
````
