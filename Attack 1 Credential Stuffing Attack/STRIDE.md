```mermaid

graph TD
    subgraph User Interaction
        A[Attacker] -->|HTTP Requests| B[CloudVista Login Endpoint]
    end

    subgraph Web Server
        B -->|Authenticate| C[Authentication Service]
        B -->|Log Activity| D[Logging Service]
    end

    subgraph Backend Infrastructure
        C -->|Query| E[Database]
        C -->|Process| F[Account Recovery Service]
    end


    %% Threats
    T1([Spoofing: Use Stolen Credentials]) -.-> A
    T2([Tampering: Modify Login Payloads]) -.-> B
    T3([Repudiation: Deny Unauthorized Login]) -.-> D
    T4([Information Disclosure: Expose User Data]) -.-> E
    T5([Denial of Service: Overload Login Endpoint]) -.-> B
    T6([Elevation of Privilege: Modify Account Settings]) -.-> F

    %% Mitigations
    M1([Mitigation: Strong Authentication]) --> T1
    M2([Input Validation and HTTPS]) --> T2
    M3([Audit Logs and Alerts]) --> T3
    M4([Data Encryption and Access Control]) --> T4
    M5([Rate Limiting and CAPTCHA]) --> T5
    M6([Restrict Recovery Mechanisms]) --> T6