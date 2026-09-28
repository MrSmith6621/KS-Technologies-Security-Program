# KS Technologies Security Program

A hands-on cybersecurity portfolio project simulating the design, implementation, hardening, and monitoring of a fictional enterprise environment.

The project is being developed progressively to demonstrate practical skills across networking, infrastructure security, identity and access management, security monitoring, vulnerability management, and incident response.

> KS Technologies is a fictional organisation created solely for cybersecurity training and portfolio development.

---

## Project Objectives

The objective of this project is to build a realistic enterprise environment and apply security controls using a defence-in-depth approach.

Rather than completing isolated labs, each phase contributes to the security program of the same fictional organisation.

Key areas include:

- Asset management
- Network segmentation
- Access control
- Least privilege
- Secure administration
- Server and endpoint security
- Identity and access management
- Security monitoring
- Vulnerability management
- Incident detection and response

---

## Current Environment

The simulated KS Technologies network currently contains:

| Component | Implementation |
|---|---|
| Departments | IT, Finance, HR, Sales, Operations and Management |
| Network Segmentation | Dedicated VLANs for departments, management, guests and servers |
| Routing | Router-on-a-stick with 802.1Q |
| Servers | Domain Controller and File Server |
| Network Security | Extended and standard ACLs |
| Guest Security | Isolated from corporate networks |
| Administrative Access | Dedicated privileged IT workstation |
| Device Management | SSH v2 with Telnet disabled |
| Management Network | Dedicated VLAN 60 |
| Switch Hardening | Unused interfaces administratively disabled |

---

## Project Phases

### 01 — Company Overview
Defines the fictional organisation, departments, infrastructure requirements and security objectives.

### 02 — Asset Inventory
Creates an inventory of company assets with ownership, criticality and data-classification information.

### 03 — Network Security ✅
Designed and implemented the enterprise network in Cisco Packet Tracer.

Implemented controls include:

- Eight VLANs
- Inter-VLAN routing
- 802.1Q trunking
- Department isolation
- Guest network isolation
- Server VLAN protection
- Service-level access control
- Privileged administrative workstation separation
- SSH-only network-device management
- Management-plane restrictions
- Disabled unused switch interfaces

Security controls were tested using both permitted and denied traffic to verify that access-control policies operated as intended.

### 04 — Security Monitoring
Planned: centralised logging, security-event generation, monitoring and investigation.

### 05 — Identity & Access Management
Planned: users, groups, roles, privileged access and least-privilege identity controls.

### 06 — Vulnerability Management
Planned: vulnerability identification, prioritisation, remediation and validation.

### 07 — Incident Response
Planned: simulated security incidents, investigation, containment and documentation.

---

## Repository Structure

```text
KS-Technologies-Security-Program/
├── 01-Company-Overview/
├── 02-Asset-Inventory/
├── 03-Network-Security/
│   ├── Screenshots/
│   ├── KS-Technologies-Network.pkt
│   └── network-design.md
└── README.md