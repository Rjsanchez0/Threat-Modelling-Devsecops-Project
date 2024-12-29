```mermaid
sequenceDiagram
    participant Attacker
    participant CloudVistaApp
    participant BackendServer
    participant Database

    activate Attacker
    Attacker->>CloudVistaApp: Identify Transaction API Endpoint
    CloudVistaApp->>Attacker: API Details Returned
    deactivate Attacker

    activate Attacker
    Attacker->>CloudVistaApp: Send Tampered Request (e.g., modified user_id)
    CloudVistaApp->>BackendServer: Process Malicious Transaction
    BackendServer->>Database: Query Unauthorized User Data
    Database->>BackendServer: Data Returned
    BackendServer->>Attacker: Unauthorized Data and Transaction Success
    deactivate Attacker
