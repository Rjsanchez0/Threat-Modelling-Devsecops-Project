# Attack 3: Insider Threat via Misconfigured IAM Policies
##

##  Stages of the Attack

### 1. Reconnaissance
An insider (e.g., a disgruntled employee) identifies overly permissive IAM policies within CloudVista Solutions’ AWS environment. Using their legitimate access, they explore roles and permissions to find potential vulnerabilities.

### 2. Weaponization
The insider crafts queries or scripts to exploit excessive permissions, targeting sensitive data stored in AWS S3 buckets or databases. For example, they may locate and use a role that allows unrestricted access to the organization’s financial logs.

### 3. Delivery
The insider leverages the misconfigured IAM policies to perform unauthorized actions, such as downloading sensitive files from S3 buckets or altering database records.

### 4. Exploitation
By exploiting the excessive permissions, the insider gains access to sensitive customer PII, financial records, or confidential company information.

### 5. Installation
The insider establishes persistence by creating additional IAM roles or policies with similar excessive permissions, enabling future unauthorized access.

### 6. Command and Control
Exfiltrated data is transferred to external storage systems or sold on the dark web. Alternatively, the insider may communicate with external threat actors to execute further malicious activities.

### 7. Action on Objectives
The attacker achieves their goal by leaking sensitive data, sabotaging critical systems, or using stolen information for financial gain or revenge.

```mermaid
flowchart LR
    Recon[Reconnaissance: Identify Misconfigured IAM Policies] --> Weapon[Weaponization: Craft Malicious Queries or Scripts]
    Weapon --> Delivery[Delivery: Exploit Excessive IAM Permissions]
    Delivery --> Exploitation[Exploitation: Access Sensitive Data or Systems]
    Exploitation --> Installation[Installation: Create New IAM Roles or Policies]
    Installation --> C2[Command and Control: Exfiltrate Data to External Systems]
    C2 --> Objectives[Action on Objectives: Sabotage or Financial Gain]
