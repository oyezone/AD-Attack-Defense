# Active Directory Attack + Defense Lab

Enterprise-style Active Directory security engineering project demonstrating realistic attack simulation, detection validation, and defensive hardening.

---

## Executive Summary

This project models a corporate Active Directory environment and walks through the complete identity security lifecycle:

Architecture → Attack Simulation → Detection Engineering → Hardening → Validation

The objective was to simulate realistic AD attack paths, generate authentication telemetry, enforce defensive controls, and validate measurable security posture improvement.

Environment:

- Domain: corp.local
- Domain Controller: DC01 (192.168.1.214)
- Workstation: OYE (192.168.1.193)
- Roles: AD DS, DNS
- Log Source: Windows Security Log

---

## Repository Structure

### Architecture
Environment topology, trust boundaries, and attack surface analysis.

→ [Architecture Overview](architecture/architecture-overview.md)

---

### Attack Simulation
Kerberos exposure, privilege escalation, command execution telemetry, and authentication pattern analysis.

→ [Attack Scenarios](attack-simulation/attack-scenarios.md)

---

### Detection Engineering
Audit configuration, event validation, and MITRE ATT&CK alignment.

→ [Detection Controls](detection-engineering/detection-controls.md)

---

### Hardening
Defensive measures applied to reduce identity attack surface and enforce stronger security posture.

→ [Hardening Actions](hardening/hardening-actions.md)

---

### Findings Summary
Enterprise-style audit checklist and post-control validation results.

→ [Audit Checklist](findings-summary/audit-checklist.md)

---

## Evidence

All validation artifacts are stored in:

`/evidence`

Evidence is contextually linked within each relevant documentation section.

---

## Security Impact

Demonstrated practical Active Directory security engineering capability across:

- Identity threat modeling
- Kerberos security analysis
- Privileged access monitoring
- Audit configuration
- Defensive hardening validation
