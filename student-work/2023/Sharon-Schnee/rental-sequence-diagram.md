## Sequence Diagram - Apartment Rental

```mermaid
   sequenceDiagram
   Renter->>Agent: "I'd like to rent a three-bedroom apartment, on a low floor."
   Renter-->Agent: They go to an apartment
   Renter->>Agent: "This is a five-bedroom penthouse!"
   Agent->>Renter: "It's got great air and light! Plenty of storage."
   Renter-->Agent: They go to another apartment.
   Renter->>Agent: "This looks great. I'll take it."
   Agent->>Owner: "We have a renter for the apartment."
   Owner->>Lawyer: "Please write up a contract to rent out my apartment."
   Lawyer-->>Owner: Gives owner prepared contract.
   Owner->>Agent: "Have the renter sign this."
   Agent->>Renter: "Here's the contract. Please sign it and return it to me."
   Renter-->>Agent: Tenant returns the signed contract to the agent.
   Agent->> Owner: "Here is the contract from the renter."
   Owner->>Lawyer: "Here is the contract signed by the tenant."
   Owner-->>Lawyer: The owner signs the rental contract and pays the lawyer's fee
   Owner->>Agent: "Have the renter meet me at the apartment to pick up the keys."
   Agent->>Renter: "Meet the owner at the apartment to pick up the keys."
   Renter->>Owner: "Hi, I'd like to pick up the keys. Here are first and last months rent, and security deposit."
   Owner-->>Renter: Gives renter the keys to the apartment.
   Renter-->>Agent: Pays fee to the agent.
   Owner-->>Agent: Pays fee to the agent.
   ```
