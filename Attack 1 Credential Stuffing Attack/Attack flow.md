```mermaid
sequenceDiagram
    participant Attacker
    participant CloudVistaApp
    participant BackendServer
    participant UserAccount

    activate Attacker
    Attacker->>CloudVistaApp: Identify login endpoint
    CloudVistaApp->>Attacker: Endpoint information retrieved
    deactivate Attacker

    activate Attacker
    Attacker->>CloudVistaApp: Prepare stolen credentials
    CloudVistaApp->>Attacker: No rate limiting or bot detection identified
    deactivate Attacker

    activate Attacker
    Attacker->>CloudVistaApp: Launch automated login attempts
    CloudVistaApp->>Attacker: Successful login with valid credentials
    deactivate Attacker

    activate Attacker
    Attacker->>UserAccount: Modify account recovery details
    UserAccount->>Attacker: Recovery email/phone updated
    deactivate Attacker

    activate Attacker
    Attacker->>BackendServer: Perform unauthorized transactions
    BackendServer->>Attacker: Transactions processed successfully
    Attacker->>BackendServer: Exfiltrate user data
    BackendServer->>Attacker: Data exfiltrated
    deactivate Attacker
