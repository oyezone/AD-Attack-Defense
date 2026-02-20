# Active Directory Attack + Defense Lab

Enterprise-grade Active Directory security lab demonstrating realistic attack simulation, detection engineering, and defensive hardening validation.

---

## Executive Summary

This project simulates a corporate Active Directory environment to model real-world attack paths and validate defensive controls.

Objectives:

- Identify Active Directory attack surfaces
- Generate authentic authentication telemetry
- Enable enterprise-level audit visibility
- Harden exposed configurations
- Validate measurable security posture improvement

This lab emphasizes security engineering principles rather than tool execution.

---


## Evidence Reference Matrix

All validation artifacts are located in the `/evidence` directory.

| Control / Scenario | Event ID | Screenshot File |
|--------------------|----------|------------------|
| DC01 IP Configuration | N/A | evidence/01-architecture-dc01-ipconfig.png |
| Workstation IP Configuration | N/A | evidence/02-architecture-workstation-ipconfig.png |
| OU Structure | N/A | evidence/03-ou-structure.png |
| Admin Logon Restriction GPO | N/A | evidence/04-gpo-admin-logon-restriction.png |
| Advanced Audit Policy Enabled | N/A | evidence/05-gpo-advanced-audit-policy.png |
| Admin Logon Block Validation | 4625 | evidence/06-admin-login-blocked.png |
| User Created | 4720 | evidence/07-attack-user-created-4720.png |
| Added to Domain Admins | 4732 | evidence/08-attack-added-to-admins-4732.png |
| User Deleted | 4726 | evidence/09-attack-user-deleted-4726.png |
| Process Creation (Command Line Logging) | 4688 | evidence/10-attack-process-creation-4688.png |
| SPN Configuration | N/A | evidence/11-kerberos-spn-configured.png |
| Kerberos TGS Request (RC4 0x17) | 4769 | evidence/12-kerberos-tgs-request-4769-rc4.png |
| Kerberos Hardened to AES (0x12) | 4769 | evidence/13-kerberos-encryption-hardened-aes.png |
| Logon Type 3 (Network) | 4624 | evidence/14-logon-type-3-network.png |
| Logon Type 10 (RDP) | 4624 | evidence/15-logon-type-10-rdp.png |

## Lab Environment

| Component | Value |
|-----------|--------|
| Domain | corp.local |
| Domain Controller | DC01 (192.168.1.214) |
| Workstation | OYE (192.168.1.193) |
| Server Roles | AD DS, DNS |
| Log Source | Windows Security Log |
| Administrative Model | corp\Administrator, corp\oye.admin, ws.admin |

---

## Attack Scenarios Simulated

| Technique | Events Generated |
|-----------|------------------|
| Service Account + SPN Exposure | 4769 |
| Privilege Escalation Simulation | 4720 / 4732 / 4726 |
| Command Execution Monitoring | 4688 |
| Logon Pattern Analysis | 4624 (Type 3 / Type 10) |

---

## Detection Engineering Implemented

- Advanced Audit Policy configured and validated
- Process creation logging with command-line arguments enabled (Event ID 4688)
- Kerberos TGS request monitoring validated (Event ID 4769)
- Logon type differentiation verified (Network vs RDP)
- Administrative group modification visibility confirmed

---

## Hardening Measures Applied

- Enforced AES-only Kerberos encryption (RC4 disabled)
- Restricted privileged account logon scope via GPO
- Reviewed and validated Domain Admin group membership
- Reduced Kerberoast exposure surface
- Validated telemetry improvements post-hardening

---

## Validation Results

| Control | Result |
|----------|--------|
| Command-line logging (4688) | Verified |
| Kerberos monitoring (4769) | Verified |
| Privilege change detection | Verified |
| Logon type visibility | Verified |
| RC4 encryption disabled | Confirmed (AES enforced) |

---

## Evidence

All supporting screenshots and validation artifacts are available in the `evidence/` directory.

Key evidence includes:

- Architecture validation
- OU and GPO enforcement
- Privilege escalation telemetry
- Kerberos encryption transition (RC4 → AES)
- Logon type analysis



---

## Evidence Reference Matrix

All validation artifacts are located in the `/evidence` directory.

| Control / Scenario | Event ID | Screenshot File |
|--------------------|----------|------------------|
| DC01 IP Configuration | N/A | evidence/01-architecture-dc01-ipconfig.png |
| Workstation IP Configuration | N/A | evidence/02-architecture-workstation-ipconfig.png |
| OU Structure | N/A | evidence/03-ou-structure.png |
| Admin Logon Restriction GPO | N/A | evidence/04-gpo-admin-logon-restriction.png |
| Advanced Audit Policy Enabled | N/A | evidence/05-gpo-advanced-audit-policy.png |
| Admin Logon Block Validation | 4625 | evidence/06-admin-login-blocked.png |
| User Created | 4720 | evidence/07-attack-user-created-4720.png |
| Added to Domain Admins | 4732 | evidence/08-attack-added-to-admins-4732.png |
| User Deleted | 4726 | evidence/09-attack-user-deleted-4726.png |
| Process Creation (Command Line Logging) | 4688 | evidence/10-attack-process-creation-4688.png |
| SPN Configuration | N/A | evidence/11-kerberos-spn-configured.png |
| Kerberos TGS Request (RC4 0x17) | 4769 | evidence/12-kerberos-tgs-request-4769-rc4.png |
| Kerberos Hardened to AES (0x12) | 4769 | evidence/13-kerberos-encryption-hardened-aes.png |
| Logon Type 3 (Network) | 4624 | evidence/14-logon-type-3-network.png |
| Logon Type 10 (RDP) | 4624 | evidence/15-logon-type-10-rdp.png |


---

## Security Impact

This project demonstrates the full Active Directory security lifecycle:

Build → Attack → Detect → Harden → Validate

The outcome reflects practical capability in:

- Identity security engineering
- AD telemetry analysis
- Kerberos security hardening
- Privileged access monitoring
- Enterprise audit configuration


---

## MITRE ATT&CK Mapping

| Technique | MITRE ID | Description |
|------------|----------|-------------|
| Account Manipulation | T1098 | Added user to Domain Admins group |
| Create Account | T1136 | Created new domain user |
| Kerberoasting Exposure | T1558.003 | Service account SPN ticket requested |
| Valid Accounts | T1078 | Authenticated logon using domain credentials |
| Command Execution | T1059 | Process creation telemetry monitored |

This mapping aligns simulated activity to enterprise threat modeling frameworks and validates detection coverage against known adversary behaviors.



