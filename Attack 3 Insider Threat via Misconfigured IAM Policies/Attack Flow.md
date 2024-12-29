```mermaid 
sequenceDiagram
    participant Insider
    participant CloudVistaApp
    participant IAMService
    participant Database

    activate Insider
    Insider->>CloudVistaApp: Identify Misconfigured IAM Policies
    CloudVistaApp->>Insider: Excessive Permissions Found
    deactivate Insider

    activate Insider
    Insider->>IAMService: Use Excessive Permissions to Access S3 and Databases
    IAMService->>Database: Query Sensitive Data
    Database->>IAMService: Return Data
    IAMService->>Insider: Sensitive Data Accessed
    deactivate Insider

    activate Insider
    Insider->>CloudVistaApp: Create Persistent IAM Roles for Future Access
    CloudVistaApp->>Insider: Roles Created Successfully
    deactivate Insider
