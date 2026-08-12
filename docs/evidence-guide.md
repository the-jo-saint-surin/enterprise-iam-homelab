# Evidence Capture Guide

This guide keeps the Microsoft Entra ID RBAC case study visually consistent, verifiable, and safe to publish.

## Visual standard

- **Palette:** Microsoft/Azure blue (`#0078D4`), deep navy (`#0F2747`), white, and light gray (`#F3F6F9`).
- **Canvas:** Crop every screenshot to a consistent 16:9 frame, ideally `1600 × 900 px`.
- **Content:** Retain the portal header, page title, signed-in identity where relevant, and the control or result being validated.
- **Callouts:** Use one Azure-blue outline or arrow only when the relevant field is not immediately obvious.
- **Privacy:** Redact temporary passwords, tenant IDs, subscriptions, unrelated email addresses, browser bookmarks, notifications, and personal data.
- **Integrity:** Do not reconstruct screens, alter outcomes, or add UI elements that were not present.

## Storage and filenames

Place sanitized files in `assets/screenshots/entra-rbac/`:

```text
01-test-user-list.png
02-daniel-user-administrator-role.png
03-daniel-entra-session.png
04-sarah-reset-password-action.png
05-password-reset-success.png
06a-password-reset-audit-actor.png
06b-password-reset-audit-target.png
07-least-privilege-restriction.png
```

Keep original captures outside the public repository. Commit only sanitized derivatives.

## Capture checklist and captions

### E01 — Test-user list

Capture the Entra users list with Daniel Rivera and Sarah Johnson visible.

**Caption:** *Figure 1. Cloud test identities used to validate delegated administration in the Microsoft Entra lab tenant.*

### E02 — Role assignment

Capture Daniel’s assigned roles view with **User Administrator** visible.

**Caption:** *Figure 2. Daniel Rivera assigned the User Administrator role to support scoped user-management duties.*

### E03 — Delegated session

Capture the Entra admin center while signed in as Daniel. Include enough account context to attribute the session without exposing unnecessary identifiers.

**Caption:** *Figure 3. Delegated administrator session authenticated as Daniel Rivera in the Microsoft Entra admin center.*

### E04 — Authorized action

Capture Sarah’s user page with **Reset password** visible before executing the action.

**Caption:** *Figure 4. Sarah Johnson’s standard-user record exposes the password-reset action to the delegated User Administrator.*

### E05 — Successful reset

Capture the success confirmation, fully covering the temporary password.

**Caption:** *Figure 5. Microsoft Entra confirms completion of the delegated password reset; the generated temporary password is redacted.*

### E06 — Audit event

Capture the matching audit entry. Show the activity, actor, target, result, and timestamp when available.

**Caption:** *Figure 6. Audit record correlating the password-reset activity with the delegated actor, target identity, timestamp, and result.*

The actor and target are kept as separate views so each field remains legible.

### E07 — Least-privilege restriction

Select a safe, reversible operation known to be outside the assigned role’s authority. Document the expected result before testing, then capture the unavailable control or denial. Do not attempt destructive changes merely to produce evidence.

**Caption:** *Figure 7. An out-of-scope administrative operation is unavailable or denied, demonstrating the delegated role’s permission boundary.*

Tailor the caption to the exact tested operation; do not imply a broader restriction than the evidence demonstrates.

## Quality-control checklist

- [ ] Screenshot comes from the actual lab tenant.
- [ ] Required identity, role, action, or result is legible.
- [ ] Temporary passwords and unnecessary identifiers are redacted.
- [ ] Crop uses the standard aspect ratio and dimensions.
- [ ] Caption states exactly what the artifact proves.
- [ ] Timestamp and signed-in identity are consistent across related artifacts.
- [ ] No caption claims more than the visible evidence supports.
