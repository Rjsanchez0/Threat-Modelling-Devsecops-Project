# Attack 2: API Abuse via Parameter Tampering
##

##  Stages of the Attack

### Reconnaissance
The attacker identifies and analyzes the exposed transaction API endpoint by inspecting HTTP requests and responses using tools like Burp Suite. The attacker maps input parameters and their expected responses.

### Weaponization
The attacker prepares malicious payloads by manipulating API parameters (e.g., transaction amounts, user IDs) to bypass server-side validation. These payloads are crafted to exploit logical flaws in API processing.

### Delivery
The attacker sends crafted API requests to the transaction endpoint. For example, by modifying the amount parameter, they attempt to transfer funds beyond permissible limits.

### Exploitation
The application’s backend processes the tampered requests without validating the modified parameters, allowing unauthorized transactions.

### Installation
The attacker establishes persistence by automating parameter tampering through scripts, enabling repeated exploitation.

### Action on Objectives
Unauthorized transactions are completed, transferring funds to attacker-controlled accounts. The attacker exfiltrates data such as transaction records for further misuse.

```mermaid
graph LR
    A[Attacker] -->|Reconnaissance| B[API Endpoint]
    B -->|Analyze Parameters| C[Payload Creation]
    C -->|Send Tampered Requests| D[Transaction API]
    D -->|Process Malicious Requests| E[Backend Server]
    E -->|Unauthorized Transactions| F[Attacker Account]