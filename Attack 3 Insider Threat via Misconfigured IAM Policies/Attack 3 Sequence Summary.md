# Summary MITRE ATT&CK Sequence

# Attack Description

A disgruntled employee exploits overly permissive IAM policies to access sensitive resources, exfiltrate data, and achieve malicious goals.

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

    Reconnaissance[Reconnaissance] -->|Identify excessive IAM permissions| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Prepare malicious scripts for exploitation| Delivery[Delivery]
    Delivery[Delivery] -->|Leverage IAM roles to access sensitive resources| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Download sensitive data or alter records| Installation[Installation]
    Installation[Installation] -->|Create persistent IAM roles for future access| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Exfiltrate sensitive data| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Sabotage or sell data for financial gain| Actions_Objectives[Actions on Objectives]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE_Attack fill:#D3D3D3,stroke:#000,stroke-width:2px
    Reconnaissance -->|T1592 - Gather Victim Identity Information| MITRE
    Delivery -->|T1078 - Valid Accounts| MITRE
    Exploitation -->|T1557 - Adversary-in-the-Middle| MITRE
    Installation -->|T1136 - Create Account| MITRE
    Command_Control -->|T1567 - Exfiltration Over Web Service| MITRE
    Actions_Objectives -->|T1486 - Data Manipulation| MITRE
    end
