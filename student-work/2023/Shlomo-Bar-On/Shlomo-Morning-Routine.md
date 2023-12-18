# My Morning Routine

```mermaid
   flowchart TD
   A([wake up]);
   A-->B{Awake?};
   B--Yes-->C{Does day end in Y?};
   B--No-->D[/Wake Up/];
   D-->E{Awake yet?};
   E--Yes-->C;
   E--No-->F[/**WAKE UP!!!**/];
   F-->G{Still asleep??};
   G--No-->C;
   G--Yes-->A;
   C-- No -->H[Do 100 press-ups];
   H-->I[Do 100 sit-ups];
   I-->J[Run 5 miles];
   J-->K[Take a shower];
   C--Yes-->K;
   K-->L{Feeling guilty?};
   L--Yes-->C;
   L--No-->M[Have a fresh cup of coffee];
   M-->N([Ready to face another day]);

