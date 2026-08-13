# Lab 2: Microsoft Entra Conditional Access & MFA

## Status

🚧 **In Progress — Configuration & validation pending**

This lab demonstrates how Microsoft Entra Conditional Access and multifactor authentication can be used to protect cloud identities while reducing the risk of credential-based attacks and administrative lockout.

---

## Business Scenario

An organization needs stronger authentication controls for access to cloud applications.

The security team requires selected users and administrators to complete multifactor authentication before accessing protected cloud resources.

Rather than immediately deploying the policy tenant-wide, the organization will use a controlled pilot group to test and validate the policy.

---

## Objectives

- Create a dedicated Conditional Access pilot group.
- Scope the policy to test identities.
- Configure an MFA requirement.
- Apply least-privilege and Zero Trust principles.
- Safely test the policy before broad deployment.
- Validate authentication behavior.
- Analyze Microsoft Entra sign-in logs.
- Document Conditional Access results.
- Prevent accidental administrator lockout.

---

## Architecture

```mermaid
flowchart LR
    USER["Test User"] --> SIGNIN["Microsoft Entra ID Sign-In"]

    SIGNIN --> CA["Conditional Access Policy Evaluation"]

    CA -->|"Policy Applies"| MFA["Require MFA"]

    MFA -->|"MFA Successful"| ACCESS["Cloud Application Access"]

    MFA -->|"MFA Failed / Not Completed"| DENY["Access Denied"]

    CA --> LOGS["Entra Sign-In Logs"]

    MFA --> LOGS