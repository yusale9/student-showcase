# Morning Routine

```mermaid
   flowchart TD
   A((Start))-->B[Wake up];
   B-->C[Take a shower];
   C-->D[Get dressed];
   D-->E{Am I hungry?};
   E-.-Yes-.->F[Have a proper breakfast];
   E-.-No-.->G[Drink tea];
   F-->H[Go to work];
   G-->H;
   H-->I[Read some book on my way to work];
   I-->J[Arrive to work];
   J-->K((End));   
