# Interview Points

## RBAC / Group-Based Access Principle

Users should not be assigned permissions directly. Instead, they should be placed into groups and permissions should be assigned to those groups.

This improves scalability, simplifies access management and reduces the risk of misconfiguration or excessive permissions.

In this project:
- Users (e.g. bob.finance) are assigned to groups (Finance Users)
- Access is controlled at the group level rather than per user
