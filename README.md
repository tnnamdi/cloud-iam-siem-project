# Detecting Suspicious Cloud Logins with IAM Controls

## Objective

This project simulates a compromised cloud user account and demonstrates how Identity and Access Management (IAM) controls and log analysis can be used to detect and reduce risk.

The focus is on:
- Suspicious login behavior
- IAM controls such as RBAC and MFA
- SIEM-style detection logic

---

## Scenario

A finance user account (`bob.finance`) is targeted by an attacker.

The attacker:
- Performs multiple failed login attempts
- Eventually logs in successfully
- Attempts to access resources beyond their role

IAM controls limit the impact, while logs capture the activity for detection.

---

## IAM Design

### Users
- bob.finance
- alice.hr
- charles.helpdesk
- diana.cloudadmin
- eve.security

### Groups (RBAC)
- Finance Users
- HR Users
- Helpdesk Users
- Cloud Admins
- Security Team

### Access Model
- Users are assigned to groups
- Permissions are applied at the group level
- Least privilege is enforced

---

## Security Controls

### Multi-Factor Authentication (MFA)
- Enabled for user accounts
- Prevents access with stolen credentials

### Role-Based Access Control (RBAC)
- Users are restricted to role-specific access
- Limits lateral movement if an account is compromised

### Conditional Access (Design Consideration)
- Not implemented due to licensing limitations
- Designed to enforce MFA and restrict risky logins

---

## Suspicious Activity Simulation

The following behavior was generated:

- Multiple failed login attempts
- Successful login after repeated failures
- MFA challenge during authentication

---

## Log Analysis

Azure Sign-in logs were used to analyze activity.

Observed pattern:
- Several failed login attempts
- Followed by a successful login
- Indicates possible credential compromise

---

## Detection Logic (SIEM Thinking)

**Use Case: Failed Logins Followed by Success**

Detection rule:
- Identify multiple failed login attempts within a short time window
- Followed by a successful login

This pattern is a strong indicator of:
- Credential guessing
- Brute-force attack
- Account compromise

---

## Key Takeaways

- Identity is a primary attack surface in cloud environments
- MFA significantly reduces the risk of credential-based attacks
- RBAC limits the impact of compromised accounts
- Log analysis is essential for detecting suspicious behavior
- Detection should focus on patterns, not single events

---

## Screenshots

See `/screenshots` folder for:
- Entra ID setup
- Users and groups
- MFA configuration
- Sign-in logs showing suspicious activity
