# Threat-Modelling-Devsecops-Project
# Threat Modelling Workshop Summary

## Introduction
A 3 Hour threat modelling workshop took place to detail the runbook scenario of multiple AI attacks against the web-facing health care application CloudVista.

## Attendess
CloudVista Solutions Eng team, Product Managers, DevEx Engineers and the DevSecOps Team.

## Scope
3 Scenarios were run covering: (1) Credential Stuffing Attack, (2) API Abuse via Parameter Tampering, (3) Insider Threat via Misconfigured IAM Policies 

## Methodology
All scenarios were run against the cyber attack killchain, utilising the Mitre Att&ack framework and STRIDE for control gap assessments. Culminating in identified risks. 

## Conclusion
## correct later 
A total of 9 high risks and 4 medium risks were found during the threat modelling workshop.

## Controls Required

- Regular Security Audits Using ASVS
Perform routine security assessments using OWASP’s Application Security Verification Standard (ASVS), specifically targeting the PayFast Wallet application and its associated APIs. These audits will help identify vulnerabilities, misconfigurations, and weaknesses in its security posture.
- Patch Management
Establish a patch management policy to ensure the PayFast Wallet application, backend services, and underlying technologies (e.g., AWS, Kubernetes) are updated promptly to address known vulnerabilities. This includes automated notifications and testing of updates in staging environments before deployment.

- Comprehensive Employee Training
Conduct ongoing cybersecurity awareness training for employees, focusing on recognizing threats such as phishing, insider risks, and social engineering tactics. Include specific training for developers and DevOps engineers on secure coding practices and cloud security principles.

- Web Application Firewall (WAF)
Deploy a WAF to monitor and filter incoming traffic for malicious activity, such as SQL injection or parameter tampering. Configure the WAF to integrate seamlessly with the AWS infrastructure and enforce custom rules tailored to CloudVista’s APIs.

- Multi-factor Authentication (MFA)
Implement MFA for all user accounts, employee accounts, and administrative interfaces of the PayFast Wallet application. This will mitigate risks from credential stuffing attacks by adding an additional layer of authentication security.

- Continuous Monitoring
Utilize tools such as Amazon GuardDuty, AWS CloudTrail, and Datadog to continuously monitor network traffic, API activity, and IAM role usage. Configure alerts for anomalous activities, such as unusual API calls, excessive data downloads, or access from untrusted IPs.

- Role-based Access Control (RBAC)
Enforce RBAC across the infrastructure to restrict access to sensitive data and resources based on user roles and responsibilities. For example, limit database access to authorized personnel and prevent broad IAM roles with unrestricted permissions.

- Input Validation and API Hardening
Strengthen input validation for all API endpoints to ensure only expected and sanitized inputs are processed. Use schema validation for JSON requests, and implement rate limiting, authentication tokens, and IP whitelisting to reduce abuse risks.

- Encryption
Ensure all sensitive data in transit is secured using TLS encryption. Use AWS Key Management Service (KMS) to encrypt data at rest in S3 buckets and databases. Rotate encryption keys regularly and enforce strict access controls for decryption.

- Incident Response Plan
Develop and maintain a comprehensive incident response plan for handling breaches, insider threats, or attacks. Conduct regular drills to test response capabilities, ensuring readiness to contain and recover from incidents affecting CloudVista’s services.

- Dependency Scanning
Integrate tools such as Trivy or Snyk into the CI/CD pipeline to identify vulnerabilities in third-party libraries and container images used in the PayFast Wallet application.

- Threat Modeling
Perform ongoing threat modeling sessions during development and deployment phases to assess risks associated with new features or infrastructure changes. Leverage STRIDE methodology to address spoofing, tampering, and privilege escalation risks.



# Threat Modelling Process Summary

```mermaid
mindmap
  root((Attack Begins))
    STRIDE/MITRE ATT&CK/Kill Chain
      Conduct Inherent Risk Assesment
      ::icon(fa fa-book)
      Create Critical Asset List
        Schedule and Scope Threat Modelling Workshop
    Controls Required
      Risks<br/>Mitigations
      Risk Summary
        Redmeiation workflow
            Slack
            JIRA 
    Attack Scenarios
      Attack 1
      Attack 2
      Attack 3
      


