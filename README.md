# Active Directory Attack + Defense Lab

Enterprise-style Active Directory security lab demonstrating realistic attack simulation, detection engineering, and defensive hardening.

---

##  Executive Summary

This project simulates a corporate Active Directory environment to:

- Identify AD attack surfaces
- Generate real authentication telemetry
- Enable enterprise-grade audit logging
- Harden exposed configurations
- Validate measurable posture improvement

Focus: security engineering, not tool execution.

---

##  Lab Environment

| Component | Value |
|------------|--------|
| Domain | corp.local |
| Domain Controller | DC01 (192.168.1.214) |
| Workstation | OYE (192.168.1.193) |
| Roles | AD DS, DNS |
| Log Source | Windows Security Log |

---

##  Attack Scenarios Simulated

| Technique | Events Generated |
|------------|------------------|
| Service Account + SPN Exposure | 4769 |
| Privilege Escalation Simulation | 4720 / 4732 / 4726 |
| Command Execution Monitoring | 4688 |
| Logon Pattern Analysis | 4624 (Type 3 / 10) |

---

## 🔎 Detection Engineering Implemented

- Advanced Audit Policy enabled
- Process creation with command-line logging validated
- Kerberos TGS monitoring configured
- Logon type differentiation validated
- Administrative group manipulation visibility confirmed

---

##  Hardening Measures Applied

- Enforced AES-only Kerberos encryption
- Restricted privileged account logon scope
- Reviewed Domain Admin group membership
- Reduced Kerberoast exposure surface

---

## 📊 Validation Results

| Control | Status |
|----------|--------|
| Command-line logging (4688) | Verified |
| Kerberos monitoring (4769) | Verified |
| Privilege change detection | Verified |
| Logon type visibility | Verified |
| RC4 disabled |  Confirmed |

---

## Evidence

All supporting screenshots and logs available in the `evidence/` directory.

---

## Outcome

Demonstrated end-to-end Active Directory security lifecycle:

Build → Attack → Detect → Harden → Validate
