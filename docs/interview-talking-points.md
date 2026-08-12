# Interview Talking Points

## 30-second summary

I built a Microsoft Entra ID lab to demonstrate delegated administration with role-based access control. I assigned a test administrator the User Administrator role rather than Global Administrator, authenticated as that identity, and completed a password reset for a standard user. The design met the support requirement while reducing unnecessary privilege. I also created a validation matrix and evidence plan covering the configuration, successful operation, audit event, and a negative authorization test.

## Why this design?

**Question:** Why didn’t you use Global Administrator?

**Answer:** Global Administrator would satisfy the functional requirement but grant far more access than a password-reset workflow needs. I selected User Administrator to align permissions to the support responsibility and reduce the blast radius of compromise or error.

## How was it validated?

**Question:** How did you know the delegation worked?

**Answer:** I validated the flow as the delegated identity, not only from the account that assigned the role. Daniel signed into the Entra admin center, accessed Sarah’s standard-user record, and completed the reset. My evidence plan also separates configuration proof, execution proof, audit correlation, and an out-of-scope restriction test.

## Authentication versus authorization

**Question:** What is the distinction in this lab?

**Answer:** Authentication established that the active administrator session belonged to Daniel. Authorization was Entra’s decision to allow the requested operation based on Daniel’s User Administrator role and the target account.

## Security value

**Question:** What risk did the control reduce?

**Answer:** It reduced standing privilege, limited access to unrelated tenant controls, and made the sensitive action attributable to a named delegated identity. That lowers the impact of credential compromise and accidental misuse, especially when the role is paired with strong authentication and audit monitoring.

## Evidence integrity

**Question:** Why are some items marked pending?

**Answer:** I distinguish what I performed from what is currently documented in the repository. I do not present an audit event or denial screenshot as evidence until I have captured, sanitized, and verified the authentic artifact.

## What would you improve in production?

I would protect privileged users with phishing-resistant MFA and Conditional Access, use Privileged Identity Management for eligible time-bound activation where licensing and policy allow, require justification and approval for sensitive activation, alert on high-risk role and password-reset activity, and periodically review assignments. I would also define a break-glass process and test recovery procedures.

## STAR outline

- **Situation:** Routine account recovery required administrative access, but tenant-wide privilege was excessive.
- **Task:** Enable a support administrator to reset a standard user’s password using least privilege.
- **Action:** Created test identities, assigned User Administrator to Daniel, authenticated as Daniel, reset Sarah’s password, and designed positive, negative, and audit validation evidence.
- **Result:** The support task succeeded without using Global Administrator for the operation; the repository transparently tracks remaining evidence work.
