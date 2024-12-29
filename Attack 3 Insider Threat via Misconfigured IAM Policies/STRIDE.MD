```mermaid
graph TD
    %% System Components
    subgraph IAM Policies
        A[Insider] -->|Use Excessive Permissions| B[IAM Roles]
    end

    subgraph CloudVista Application
        B -->|Access| C[Sensitive S3 Buckets]
        B -->|Query| D[Database Records]
    end

    %% STRIDE Threats
    T1([Spoofing: Use Legitimate Credentials]) -.-> A
    T2([Tampering: Modify IAM Roles]) -.-> B
    T3([Repudiation: Deny Unauthorized Actions]) -.-> B
    T4([Information Disclosure: Expose Confidential Data]) -.-> C
    T5([Denial of Service: Abuse IAM Permissions]) -.-> B
    T6([Elevation of Privilege: Create Persistent IAM Roles]) -.-> B

    %% Mitigations
    M1([Mitigation: Least Privilege Access]) --> T1
    M2([Mitigation: Audit IAM Policies]) --> T2
    M3([Mitigation: CloudTrail Logs]) --> T3
    M4([Mitigation: Encryption and Access Control]) --> T4
    M5([Mitigation: Role Restrictions]) --> T5
    M6([Mitigation: Multi-Factor Authentication]) --> T6
