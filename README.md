# enterprise-iam-homelab
Hands-on enterprise Identity &amp; Access Management lab covering Microsoft Entra ID, RBAC, MFA, Conditional Access, identity lifecycle management, automation, and security investigations.
## Lab 2: Microsoft Entra ID RBAC & Delegated Administration

### Objective
Implement and validate Role-Based Access Control (RBAC) in Microsoft Entra ID using delegated administrative privileges and the principle of least privilege.

### Environment
- Microsoft Entra ID
- Cloud-only tenant
- Global Administrator account
- User Administrator account
- Standard user accounts

### Scenario
The organization requires an IT administrator to manage employee accounts without granting full Global Administrator privileges.

Daniel Rivera was assigned the **User Administrator** role while Sarah Johnson remained a standard user.

### Configuration
1. Created multiple test user accounts in Microsoft Entra ID.
2. Assigned Daniel Rivera the **User Administrator** role.
3. Verified the role assignment at the directory level.
4. Signed into Microsoft Entra as Daniel Rivera.
5. Accessed Sarah Johnson's user account.
6. Initiated a password reset for Sarah.
7. Microsoft Entra successfully generated a temporary password and required a password change at next sign-in.

### Validation

**Authentication**
Daniel successfully authenticated to the Microsoft Entra admin center.

**Authorization**
Microsoft Entra evaluated Daniel's assigned administrative role and permitted authorized user-management operations.

**RBAC**
Daniel's User Administrator role allowed him to manage standard user accounts without granting Global Administrator access.

**Least Privilege**
Administrative permissions were delegated based on job responsibilities rather than providing unrestricted tenant administration.

### Result

✅ User Administrator role successfully assigned  
✅ Delegated administrator successfully authenticated  
✅ Standard user password successfully reset  
✅ RBAC permissions successfully validated  
✅ Global Administrator privileges were not required

### Security Takeaway
This lab demonstrates how Microsoft Entra ID RBAC can reduce unnecessary administrative privilege while still allowing IT personnel to perform required support operations.
