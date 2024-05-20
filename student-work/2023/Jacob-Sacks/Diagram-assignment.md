# Morning Routine

```mermaid

flowchart TD;
A((Wake up))-->B{Is Avigail awake?};
B-- Yes -->C(Take Avigail out of her crib.);
B-- No -->D(Go to the bathroom.);
D-->E(Get dressed.);
E-->F(Wait for Avigail to wake up.);
F-- Avigail wakes up -->C;
C-->G(Change her diaper.);
G-->H(Brush her teeth.);
H-->I(Get her bib, spoon, and food.);
I-->J(Put her in her high-chair and give her breakfast.);
J-->K{Are you dressed?};
K-- No -->L(Go to the bathroom.);
L-->M(Get dressed.);
M-->N;
K-- Yes -->N(Get clothes for Avigail.);
N-->O(After Avigail is done eating, get her dressed.);
O-->P(Put her in her stroller.);
P-->Q(Pur her shoes on.);
Q-->R{Is it cold?};
R-- Yes -->S(Put a jacket on her.);
R-- No -->T(Bring her to gan.);
S-->T;
T-->U(Go to minyan.);
U-->V(Go home and start working.);

```

# Renting an apartment

```mermaid

sequenceDiagram
participant E as Renter
participant O as Realtor
participant L as Landlord
L->>O: Hire realtor to find potential renter
O->>E: Find potential renter
E->L: Agree on a date/time to check the apartment
E->>L: Renter comes to check apartment
Note over E: Likes apartment
E->L: Negotiate terms of rental
L->>E: Draw up contract
E->>L: Sign contract
E->>O: Pay realtor
L->>O: Pay realtor
E->>L: Give security deposit
L->>E: Give keys on agreed upon date
E->>L: Pay monthly rent payments
E->>L: Notify landlord before end of rental if they're moving out

```
