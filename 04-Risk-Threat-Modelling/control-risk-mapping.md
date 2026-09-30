# KS Technologies — Control-to-Risk Mapping

## Purpose

This document maps the cybersecurity risks identified during threat modelling to the security controls implemented or planned within the KS Technologies Security Program.

The objective is to demonstrate that security controls are implemented in response to identified risks and business requirements rather than as isolated technical configurations.

---

## Control-to-Risk Matrix

| Risk | Security Control | Status | Evidence / Phase |
|---|---|---|---|
| R-001 — Phishing & credential theft | Network segmentation and restricted cross-VLAN access | Implemented | Phase 03 — Network Security |
| R-001 — Phishing & credential theft | Identity protection and authentication monitoring | Planned | Identity & Access Management |
| R-002 — Endpoint compromise & lateral movement | Departmental VLAN segmentation | Implemented | Phase 03 — Network Security |
| R-002 — Endpoint compromise & lateral movement | Inter-VLAN ACLs | Implemented | Phase 03 — Network Security |
| R-002 — Endpoint compromise & lateral movement | Endpoint monitoring and detection | Planned | Security Monitoring & Detection |
| R-003 — Unauthorised HR/Finance access | HR and Finance VLAN isolation | Implemented | Phase 03 — Network Security |
| R-003 — Unauthorised HR/Finance access | Role-based access control | Planned | Identity & Access Management |
| R-004 — Guest access to corporate resources | Dedicated Guest VLAN 70 | Implemented | Phase 03 — Network Security |
| R-004 — Guest access to corporate resources | Guest-to-corporate ACL restrictions | Implemented | Phase 03 — Network Security |
| R-005 — Unauthorised server access | Dedicated Server VLAN 80 | Implemented | Phase 03 — Network Security |
| R-005 — Unauthorised server access | Service-level ACL restrictions | Implemented | Phase 03 — Network Security |
| R-005 — Unauthorised server access | Vulnerability scanning and patch management | Planned | Vulnerability Management |
| R-006 — Administrator account compromise | SSHv2 remote administration | Implemented | Phase 03 — Network Security |
| R-006 — Administrator account compromise | Telnet disabled | Implemented | Phase 03 — Network Security |
| R-006 — Administrator account compromise | Dedicated Management VLAN 60 | Implemented | Phase 03 — Network Security |
| R-006 — Administrator account compromise | Restricted management access | Implemented | Phase 03 — Network Security |
| R-006 — Administrator account compromise | Privileged identity monitoring | Planned | Identity & Access Management |
| R-007 — Internal network reconnaissance | Network segmentation and ACLs | Implemented | Phase 03 — Network Security |
| R-007 — Internal network reconnaissance | Network activity detection | Planned | Security Monitoring & Detection |
| R-008 — Vulnerable or misconfigured service | Network device hardening | Implemented | Phase 03 — Network Security |
| R-008 — Vulnerable or misconfigured service | Unused switch ports disabled | Implemented | Phase 03 — Network Security |
| R-008 — Vulnerable or misconfigured service | Vulnerability scanning | Planned | Vulnerability Management |
| R-009 — Security control misconfiguration | Configuration verification and connectivity testing | Implemented | Phase 03 — Network Security |
| R-009 — Security control misconfiguration | Formal change control | Planned | Security Operations & Governance |
| R-010 — Malicious activity goes undetected | Centralised security logging | Planned | Security Monitoring & Detection |
| R-010 — Malicious activity goes undetected | Detection rules and alert triage | Planned | Security Monitoring & Detection |

---

## Implemented Control Evidence

Phase 03 provides practical evidence for several controls identified within the risk register.

Evidence includes:

- VLAN configuration
- 802.1Q trunk configuration
- Router subinterfaces
- Inter-VLAN connectivity testing
- Access-port VLAN assignments
- ACL verification
- Guest network isolation
- HR and Finance isolation
- Restricted Finance service access
- Denied unauthorised server access
- SSH-enabled remote administration
- Telnet disabled
- Restricted switch management
- Disabled unused switch ports

Supporting screenshots and the Cisco Packet Tracer environment are retained within the `03-Network-Security` directory.

---

## Security Program Progression

The control mapping demonstrates how each phase of the KS Technologies Security Program contributes to reducing identified cybersecurity risks.

The current environment relies primarily on preventative network controls.

Future phases will introduce additional layers including:

- Security monitoring and detection
- Identity and access management
- Endpoint security
- Vulnerability management
- Incident response
- Security governance

As these controls are implemented, the risk register will be reassessed and residual risk will be documented.

---

## Defence-in-Depth Approach

KS Technologies follows a defence-in-depth approach.

No single security control is expected to prevent every attack. Instead, multiple preventative, detective, and responsive controls are combined to reduce the likelihood and impact of a security incident.

For example: Network Segmentation → ACL Enforcement → Restricted Server Access → Security Monitoring → Alert Investigation → Incident Response
