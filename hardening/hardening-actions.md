# Hardening Actions

## Initial Risk Conditions

- RC4 encryption permitted for Kerberos
- No validated command-line logging
- Broad admin logon scope
- Privilege monitoring not verified

---

## Defensive Controls Applied

- Disabled RC4 encryption
- Enforced AES-only Kerberos (0x12 confirmed)
- Enabled command-line process logging
- Applied GPO-based admin logon restrictions
- Validated privilege change telemetry

---

## Post-Hardening Validation

- RC4 no longer observed in TGS requests
- AES encryption confirmed
- Admin logon restrictions enforced
- Privilege manipulation fully logged

Hardening actions resulted in measurable identity security posture improvement.

## Supporting Evidence

- Admin Logon Restriction  
  ![Admin Block](../evidence/06-admin-login-blocked.png)

- Kerberos AES Enforcement  
  ![AES](../evidence/13-kerberos-encryption-hardened-aes.png)
