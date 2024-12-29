```mermaid
graph TD
    %% System Components
    subgraph User Interaction
        A[Attacker] -->|Tampered Requests| B[Transaction API]
    end

    subgraph CloudVista Application
        B -->|Query| C[Backend Server]
        B -->|Log Requests| D[Logging Service]
    end

    subgraph Backend Infrastructure
        C -->|Access| E[Database]
    end

    %% STRIDE Threats
    T1([Spoofing: Use Compromised Tokens]) -.-> A
    T2([Tampering: Modify API Parameters]) -.-> B
    T3([Repudiation: Deny API Requests]) -.-> D
    T4([Information Disclosure: Access Sensitive Data]) -.-> E
    T5([Denial of Service: Flood API]) -.-> B
    T6([Elevation of Privilege: Access Unauthorized Data]) -.-> C

    %% Mitigations
    M1([Mitigation: OAuth2 Authentication]) --> T1
    M2([Mitigation: Input Validation]) --> T2
    M3([Mitigation: Audit Logs]) --> T3
    M4([Mitigation: Encryption and RBAC]) --> T4
    M5([Mitigation: Rate Limiting]) --> T5
    M6([Mitigation: Role-Based Access Control]) --> T6
