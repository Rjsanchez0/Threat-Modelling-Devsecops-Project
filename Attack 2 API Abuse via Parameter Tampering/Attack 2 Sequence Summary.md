# Summary MITRE ATT&CK Sequence

# Attack Description

Attackers exploit the Transaction API by tampering with parameters to bypass limits and access unauthorized data. This leads to unauthorized transactions, data breaches, and financial losses

```mermaid
flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#D3D3D3,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Attacker identifies Transaction API endpoint| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Craft tampered API requests with malicious parameters| Delivery[Delivery]
    Delivery[Delivery] -->|Send malicious API requests exploiting validation flaws| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Gain unauthorized access to user accounts or data| Installation[Installation]
    Installation[Installation] -->|Create fraudulent transactions or update recovery info| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Exfiltrate sensitive data| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Steal user financial data| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Perform unauthorized financial transactions| Actions_Objectives[Actions on Objectives]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE_Attack fill:#D3D3D3,stroke:#000,stroke-width:2px
    Reconnaissance -->|T1595 - Active Scanning| MITRE
    Delivery -->|T1190 - Exploit Public-Facing Application| MITRE
    Exploitation -->|T1078 - Valid Accounts| MITRE
    Installation -->|T1565 - Data Manipulation| MITRE
    Command_Control -->|T1567 - Exfiltration Over Web Service| MITRE
    Actions_Objectives -->|T1486 - Data Manipulation| MITRE
    Actions_Objectives -->|T1213 - Access Data from Repositories| MITRE
    end
