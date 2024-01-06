## Sequence Diagram - Apartment Rental

```mermaid
   sequenceDiagram
   Renter->>Agent: The renter approaches the agent to see an apartment.
    Agent->>Renter: The agent takes the renter to apartments.
   Renter->>Agent: Renter chooses an apartment to rent.
   Agent->>Owner: Agent informs owner there is a renter for the apartment.
   Owner->>Lawyer: The owner approaches his lawyer to get a contract for the rental agreement.
   Lawyer->>Owner: The lawyer draws up a contract for the owner.
   Owner->>Agent: The owner asks the agent to get the contract signed by renter.
   Agent->>Renter: The agent approaches the renter to sign the contract.
   Renter->>Agent: Tenant returns the signed contract to the agent.
   Agent->> Owner: Agent gives it to the owner.
   Owner->>Lawyer: Signs and gives it to the lawyer.
   Owner->>Agent: The owner has the agent set up a time with the renter to transfer keys.
   Agent->>Renter: The agent sets a time with the renter for the owner to hand over keys.
   Renter->>Owner: The renter makes initial payments and gets keys.
   Owner->>Renter: Gives renter the keys to the apartment.
   Renter->>Agent: Pays fee to the agent.
   Owner->>Agent: Pays fee to the agent.
   ```
