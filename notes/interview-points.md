# Interview Points

## RBAC / Group-Based Access Principle

Users should not be assigned permissions directly. Instead, they should be placed into groups and permissions should be assigned to those groups.

This improves scalability, simplifies access management and reduces the risk of misconfiguration or excessive permissions.

In this project:
- Users (e.g. bob.finance) are assigned to groups (Finance Users)
- Access is controlled at the group level rather than per user

## MFA (Multi-Factor Authentication)

MFA adds a second layer of verification beyond just a password.

Why it matters:
Even if an attacker obtains valid credentials, they cannot access the account without the second factor.

In this project:
- MFA is enabled for user accounts
- This helps prevent unauthorized access even if credentials are compromised
