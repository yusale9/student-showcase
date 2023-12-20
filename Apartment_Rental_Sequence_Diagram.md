# Apartment Rental Sequence Diagram
```mermaid
sequenceDiagram;
    participant Lawyer
    participant Tenant
    participant Agent
    participant Landlord
    Tenant->>Agent: Asks about apartments to rent
    Agent->>Tenant: Provides list of suitable apartments
    Tenant->>Agent: Chooses Landlord's apartment
    Landlord->Tenant: Arrange viewing times
    Tenant->>Landlord: Arrives at appointed time
    Agent->>Landlord: Arrives at appointed time
    Agent->>Tenant: Shows apartment with all its features
    Tenant->>Landlord: Expresses interest in renting apartment
    Tenant->Landlord: Arrange time to sign rental contract
    Agent->Tenant: Sign a conditional payment contract
    Landlord->>Tenant: Sends a draft of rental contract
    Tenant->>Lawyer: Asks to review clause in contract
alt Contract needs changes
    Lawyer->>Tenant: Makes suggestions to contract
    Landlord->Tenant: Negotiate what to add/subtract
else Lawyer->>Tenant: Approves contract as is
end
    Tenant->>Landlord: Arrives to sign contract

    


