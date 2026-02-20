## Architecture Diagram

                         +----------------------+
                         |      DC01            |
                         |  Windows Server 2022 |
                         |  Role: AD DS + DNS   |
                         |  IP: 192.168.1.214   |
                         +----------+-----------+
                                    |
                                    |  Kerberos (TCP/UDP 88)
                                    |  LDAP (389)
                                    |  SMB (445)
                                    |
                         +----------v-----------+
                         |        OYE           |
                         |  Domain Workstation  |
                         |  IP: 192.168.1.193   |
                         +----------------------+

        Domain: corp.local
        Authentication Authority: DC01
        Log Source: Windows Security Log (DC01)

        ## Trust Model

- DC01 acts as the Kerberos Key Distribution Center (KDC).
- OYE authenticates to DC01 for ticket-granting tickets (TGT) and service tickets (TGS).
- Service account (corp\svc-sql) introduces Kerberos SPN attack surface.
- All security telemetry validated from DC01 Security Log.
# Architecture Overview


## Environment Summary

This lab models a simplified enterprise Active Directory identity environment.

| Component | Details |
|------------|----------|
| Domain | corp.local |
| Domain Controller | DC01 (192.168.1.214) |
| Workstation | OYE (192.168.1.193) |
| Roles | AD DS, DNS |
| Log Source | Windows Security Log |

## Administrative Model

- corp\Administrator – Domain Admin
- corp\oye.admin – Delegated Admin
- ws.admin – Workstation Admin
- corp\svc-sql – Service Account (SPN enabled)

## Identity Trust Boundaries

- Domain Controller hosts authentication authority.
- Workstation consumes Kerberos tickets from DC.
- Service account configured with SPN exposes Kerberos TGS request surface.

## Attack Surface Areas Identified

- Service account Kerberos exposure (Kerberoasting risk)
- Privileged group membership manipulation
- Lateral movement via valid accounts
- Insufficient logging visibility (pre-hardening)

Architecture validation evidence located in `/evidence`.


## Supporting Evidence

- DC01 IP Configuration  
  ![DC01 IP](../evidence/01-architecture-dc01-ipconfig.png)

- Workstation IP Configuration  
  ![Workstation IP](../evidence/02-architecture-workstation-ipconfig.png)

- OU Structure  
  ![OU Structure](../evidence/03-ou-structure.png)
