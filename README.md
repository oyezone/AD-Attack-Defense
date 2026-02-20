## Overview

This project simulates a hybrid enterprise Active Directory environment to demonstrate a full attack-to-defense lifecycle within a Windows domain.

The lab was designed to replicate real-world security engineering workflows, including:

- Active Directory misconfiguration analysis
- Kerberos service ticket abuse simulation (Kerberoast surface)
- Privilege escalation detection
- Authentication telemetry analysis
- Advanced audit policy configuration
- Defensive hardening validation

Rather than focusing solely on offensive tooling, this project emphasizes controlled attack simulation followed by measurable defensive improvement.

The goal was not only to generate attack telemetry, but to:

- Enable enterprise-grade logging
- Validate detection visibility
- Reduce attack surface exposure
- Confirm security posture improvements through evidence

This reflects the responsibilities of modern Security Engineers, Detection Engineers, and Blue Team practitioners operating in corporate Active Directory environments.

## Lab Architecture

### Domain Information
- Domain Name: corp.local
- Forest Level: Windows Server 2025
- Functional Scope: Single-domain lab environment

### Domain Controller
- Hostname: DC01.corp.local
- Role: Active Directory Domain Services (AD DS) + DNS
- IP Address: 192.168.1.214
- Default Gateway: 192.168.1.254
- Primary Log Source: Windows Security Log

### Domain Workstation
- Hostname: OYE.corp.local
- Role: Domain-joined client
- IP Address: 192.168.1.193
- DNS Server: 192.168.1.214 (DC01)

### Authentication Flow

All authentication and attack simulations originated from the domain workstation (OYE) and were logged centrally on the Domain Controller (DC01).

Primary authentication mechanisms observed:

- Kerberos (Service Ticket Requests – Event ID 4769)
- Interactive and Remote Logons (Event ID 4624)
- Process Creation (Event ID 4688)
- Account Management Events (4720, 4732, 4726)

## What I Built

This project required building and configuring a functional Active Directory environment from the ground up.

### Infrastructure

- Deployed Windows Server as Domain Controller (DC01)
- Installed and configured Active Directory Domain Services
- Configured integrated DNS for corp.local
- Joined Windows 11 workstation to domain
- Verified domain authentication and name resolution

### Organizational Structure

- Created Organizational Units (OUs) for administrative control
- Implemented separation between standard users and administrative accounts
- Configured dedicated administrative accounts
- Reviewed Domain Admin group membership

### Group Policy Controls

- Implemented logon restriction policies
- Restricted where privileged accounts can log in
- Enabled Advanced Audit Policy configuration
- Configured process creation auditing with command-line logging

The environment was intentionally structured to simulate a small enterprise domain with realistic authentication and administrative boundaries.
