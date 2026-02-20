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

## Security Impact

This project demonstrates the full Active Directory security lifecycle:

Build → Attack → Detect → Harden → Validate

The outcome reflects practical capability in:

- Identity security engineering
- AD telemetry analysis
- Kerberos security hardening
- Privileged access monitoring
- Enterprise audit configuration
