# KS Technologies — Security Objectives

## Purpose

The purpose of the KS Technologies security program is to protect company systems, users, and information while allowing each department to perform its required business functions.

Security controls are selected according to business risk and follow the principles of defence in depth, least privilege, network segmentation, and administrative separation.

The environment is designed around the assumption that individual endpoints or user accounts may eventually become compromised. Controls should therefore reduce the likelihood that a single compromise can result in wider access to the organisation.

---

## Business Security Requirements

KS Technologies contains multiple departments with different responsibilities, trust levels, and information requirements.

The security architecture must:

- Protect sensitive Finance and HR information from unauthorised access.
- Allow employees to access the resources required for their roles without providing unnecessary privileges.
- Protect critical servers and infrastructure from general user access.
- Prevent guest devices from accessing internal corporate resources.
- Restrict administrative access to authorised IT personnel and systems.
- Protect the management interfaces of network infrastructure.
- Reduce opportunities for lateral movement following endpoint compromise.
- Maintain sufficient security visibility to identify and investigate suspicious activity.
- Reduce exposure to known vulnerabilities and insecure configurations.
- Support an effective response when security incidents occur.

---

## Security Objectives

### SO-01 — Protect Sensitive Departmental Data

Finance and HR process information that should not be accessible to unrelated departments.

**Objective:** Prevent unauthorised cross-department access to sensitive systems and information.

**Current controls:**
- Departmental VLAN segmentation
- Inter-VLAN ACLs
- Least-privilege access rules

---

### SO-02 — Limit Lateral Movement

A compromised employee endpoint should not provide unrestricted access to other departments or critical infrastructure.

**Objective:** Reduce the potential blast radius of an endpoint or account compromise.

**Current controls:**
- Network segmentation
- Inter-VLAN ACLs
- Dedicated server network
- Restricted administrative access

---

### SO-03 — Isolate Untrusted Guest Devices

Guest devices are not managed by KS Technologies and must therefore be treated as untrusted.

**Objective:** Prevent guest systems from communicating with corporate users, servers, or management infrastructure.

**Current controls:**
- Dedicated Guest VLAN 70
- ACL-based internal network isolation

---

### SO-04 — Protect Critical Server Infrastructure

Critical services should only be reachable where a legitimate business requirement exists.

**Objective:** Minimise unnecessary exposure of the server environment.

**Current controls:**
- Dedicated Server VLAN 80
- ACL-based server access restrictions
- Service-specific Finance access
- Restricted IT administrative access

---

### SO-05 — Secure Privileged Administration

Administrative access presents a higher level of risk than standard user activity.

**Objective:** Restrict privileged infrastructure management to authorised administrators and approved administrative systems.

**Current controls:**
- Dedicated IT administrative workstation
- SSH version 2
- Telnet disabled
- Management access ACL
- Dedicated management VLAN

---

### SO-06 — Harden Network Infrastructure

Network devices should expose only the services and interfaces required for legitimate operation.

**Objective:** Reduce the attack surface of routers and switches.

**Current controls:**
- SSH-only remote administration
- Local privileged administrator
- Login security banner
- Encrypted stored credentials
- Session timeout
- Disabled unused switch interfaces

---

### SO-07 — Improve Security Visibility

Preventive controls cannot guarantee that attacks will never occur.

**Objective:** Develop centralised visibility capable of identifying suspicious authentication, network, endpoint, and administrative activity.

**Planned controls:**
- Centralised logging
- Security event monitoring
- Detection rules
- Alert investigation

**Planned phase:** Security Monitoring & Detection

---

### SO-08 — Manage Identity and Privileged Access

Users should receive only the access required for their job responsibilities.

**Objective:** Establish controlled user provisioning, role-based access, privileged access management, and periodic access review.

**Planned phase:** Identity & Access Management

---

### SO-09 — Reduce Vulnerability Exposure

Systems and services may contain vulnerabilities or insecure configurations that could be exploited.

**Objective:** Identify, prioritise, remediate, and validate security vulnerabilities according to risk.

**Planned phase:** Vulnerability Management

---

### SO-10 — Prepare for Security Incidents

KS Technologies must be able to respond when preventative and detective controls are insufficient.

**Objective:** Establish a repeatable process for investigation, containment, remediation, recovery, and post-incident review.

**Planned phase:** Incident Response

---

## Security Strategy

KS Technologies uses a defence-in-depth approach rather than relying on a single security control.
