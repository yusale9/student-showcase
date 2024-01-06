## Sequence Diagram - Apartment Rental

```mermaid
   sequenceDiagram
   Renter->>Agent: The renter approaches the agent to see an apartment.
    Agent->>Renter: The agent takes the renter to see apartments.
   Renter->>Agent: The renter informs the agent he would like to rent a particular apartment.
   Agent->>Owner: Agent informs owner there is a renter for the apartment.
   Owner->>Lawyer: The owner approaches his lawyer to get a contract for the rental agreement.
   Lawyer->>Owner: The lawyer draws up a contract for the owner.
   Owner->>Agent: The owner asks the agent to get the contract signed by the renter.
   Agent->>Renter: The agent approaches the renter to sign the contract.
   Renter->>Agent: The renter returns the signed contract to the agent.
   Agent->> Owner: The agent gives the signed contract to the owner.
   Owner->>Lawyer: The owner signs the contract and gives it to the lawyer.
   Owner->>Agent: The owner has the agent set up a time with the renter to transfer keys.
   Agent->>Renter: The agent sets a time with the renter for the owner to hand over the keys.
   Renter->>Owner: The renter makes initial payments to the owner.
   Owner->>Renter: The owner gives the renter the keys to the apartment.
   Renter->>Agent: The renter pays a fee to the agent.
   Owner->>Agent: The owner pays a fee to the agent.
   ```
