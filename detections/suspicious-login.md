# Suspicious Login Detection

## Scenario
Multiple failed login attempts followed by a successful login.

## Why this is suspicious
- Indicates possible brute-force or credential stuffing attack
- Suggests attacker may have guessed or obtained valid credentials

## Detection Logic (SIEM-style)
- Identify multiple failed login attempts for a user within a short time window
- Followed by a successful login

## Example Logic (Plain English)
IF:
- Failed logins ≥ 3 within 5 minutes
AND
- Followed by successful login
THEN:
- Flag as suspicious activity

## Mitigation
- Enforce MFA (already implemented)
- Investigate login source (IP, location, device)
- Consider account lockout or alerting
