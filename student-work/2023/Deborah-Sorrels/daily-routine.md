```mermaid
 flowchart TD
 A((Start))-->B[Alarm Goes Off];
 B-->C{Do you want to wake up or sleep more?};
 C--Sleep More-->D[Hit the snooze button];
 D-->E[Go back to sleep];
 E-->F[Alarm goes off again];
 F-->C{Do you wan to wake up or sleep more?}; 
 C--Wake Up-->G[Turn off the alarm];
 G-->H[Get out of bed];
 H-->I[Go to the bathroom];

 I-->J{Do you want to eat or walk the dog first?};
 J--Walk the Dog-->K[Gather the leash and a poo bag];
 K-->L[Put on shoes];
 L-->M[Pick up dog and go outside];
 M-->N[Walk dog];
 N-->O[Come back inside house];
 O-->P[Wipe dog's feet];
 P-->Q[Wash hands];
 Q-->R[Feed dog];
 
