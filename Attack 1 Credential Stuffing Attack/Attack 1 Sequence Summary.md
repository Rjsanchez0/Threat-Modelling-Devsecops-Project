# Summary MITRE ATT&CK Sequence

# Attack Description

The Attackers targeted the Payfast Wallet application by exploiting compromised credentials from external breaches. This attacks seeks to gain unauthorized access to user account, leading to potential finacial fraud and data exfiltration. 

``` mermaid 
flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Resource_Development fill:#F5B041,stroke:#000,stroke-width:2px
    style Initial_Access fill:#EB984E,stroke:#000,stroke-width:2px
    style Execution fill:#E59866,stroke:#000,stroke-width:2px
    style Persistence fill:#DC7633,stroke:#000,stroke-width:2px
    style Exfiltration fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Impact fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Gather victim identity information from breach data| Resource_Development[Resource Development]
    Resource_Development[Resource Development] -->|Compile credentials and prepare bots for stuffing| Initial_Access[Initial Access]
    Initial_Access[Initial Access] -->|Automated bots test stolen credentials on login endpoints| Execution[Execution]
    Execution[Execution] -->|Authenticate successfully with valid credentials| Persistence[Persistence]
    Persistence[Persistence] -->|Modify account recovery settings to lock out users| Exfiltration[Exfiltration]
    Exfiltration[Exfiltration] -->|Export sensitive user and transaction data| Impact[Impact]
    Impact[Impact] -->|Initiate unauthorized transactions and harm reputation| Impact[Impact]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Reconnaissance -->|T1592 - Gather Victim Identity Information| MITRE
    Resource_Development -->|T1589 - Gather Credentials| MITRE
    Initial_Access -->|T1078 - Valid Accounts| MITRE
    Execution -->|T1218 - Signed Binary Proxy Execution| MITRE
    Persistence -->|T1078.003 - Credential Manipulation| MITRE
    Exfiltration -->|T1567 - Exfiltration Over Web Service| MITRE
    Impact -->|T1486 - Data Manipulation| MITRE
    end
