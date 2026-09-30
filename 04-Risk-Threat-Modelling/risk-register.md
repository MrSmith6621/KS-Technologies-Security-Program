# KS Technologies — Risk Register

## Purpose

This risk register records cybersecurity risks identified through the KS Technologies threat-modelling process.

Each risk is assessed using likelihood and impact to determine its overall risk level. Existing security controls are documented alongside additional treatment actions required to reduce the remaining risk.

The register will be reviewed as new security controls are implemented throughout the KS Technologies Security Program.

---

## Risk Rating Methodology

### Likelihood

| Rating | Description |
|---|---|
| 1 — Low | Unlikely to occur under normal circumstances |
| 2 — Medium | Could reasonably occur |
| 3 — High | Likely to occur or represents a common attack method |

### Impact

| Rating | Description |
|---|---|
| 1 — Low | Limited operational or security impact |
| 2 — Medium | Significant impact requiring investigation or remediation |
| 3 — High | Major impact involving sensitive systems, data, or business operations |

### Risk Score

**Risk Score = Likelihood × Impact**

| Score | Risk Level |
|---|---|
| 1–2 | Low |
| 3–4 | Medium |
| 6–9 | High |

---

## Risk Register

| ID | Risk | Likelihood | Impact | Score | Risk Level |
|---|---|---:|---:|---:|---|
| R-001 | Phishing and credential theft | 3 | 3 | 9 | High |
| R-002 | Compromised endpoint and lateral movement | 3 | 3 | 9 | High |
| R-003 | Unauthorised HR or Finance access | 2 | 3 | 6 | High |
| R-004 | Guest network access to corporate resources | 2 | 3 | 6 | High |
| R-005 | Unauthorised server access | 2 | 3 | 6 | High |
| R-006 | Network administrator account compromise | 2 | 3 | 6 | High |
| R-007 | Internal network reconnaissance | 2 | 2 | 4 | Medium |
| R-008 | Vulnerable or misconfigured service | 3 | 3 | 9 | High |
| R-009 | Security control misconfiguration | 2 | 3 | 6 | High |
| R-010 | Malicious activity goes undetected | 3 | 3 | 9 | High |

---

## Risk Treatment Plan

### R-001 — Phishing and Credential Theft

**Existing controls:**
- Network segmentation
- Inter-VLAN ACLs
- Restricted access between departments

**Treatment actions:**
- Implement stronger identity and authentication controls
- Monitor suspicious authentication activity
- Introduce security awareness measures
- Develop incident response procedures for compromised accounts

**Treatment:** Mitigate  
**Target phase:** Identity & Access Management / Security Monitoring

---

### R-002 — Compromised Endpoint and Lateral Movement

**Existing controls:**
- Departmental VLAN segmentation
- Inter-VLAN ACLs
- Protected server network
- Dedicated management VLAN
- Restricted privileged administration

**Treatment actions:**
- Introduce endpoint security monitoring
- Centralise security logs
- Detect suspicious network activity
- Develop containment procedures for compromised endpoints

**Treatment:** Mitigate  
**Target phase:** Security Monitoring & Detection / Endpoint Security

---

### R-003 — Unauthorised HR or Finance Access

**Existing controls:**
- Separate HR and Finance VLANs
- ACL-based departmental isolation
- Tested denied traffic between protected networks

**Treatment actions:**
- Implement role-based access control
- Perform periodic access reviews
- Monitor authentication and access activity
- Review permissions when users change roles

**Treatment:** Mitigate  
**Target phase:** Identity & Access Management

---

### R-004 — Guest Network Access to Corporate Resources

**Existing controls:**
- Dedicated Guest VLAN 70
- ACL-based isolation from corporate networks
- Connectivity testing confirming blocked internal access

**Treatment actions:**
- Monitor denied connection attempts
- Centralise network security logs
- Alert on repeated internal access attempts from the guest network

**Treatment:** Mitigate  
**Target phase:** Security Monitoring & Detection

---

### R-005 — Unauthorised Server Access

**Existing controls:**
- Dedicated Server VLAN 80
- ACL-based server access restrictions
- Restricted IT administrative access
- Finance limited to required service-level access

**Treatment actions:**
- Monitor server authentication activity
- Perform vulnerability scanning
- Establish patch and remediation procedures
- Review server access permissions periodically

**Treatment:** Mitigate  
**Target phase:** Vulnerability Management / Security Monitoring

---

### R-006 — Network Administrator Account Compromise

**Existing controls:**
- SSH version 2 for remote administration
- Telnet disabled
- Dedicated Management VLAN 60
- Management access restricted to approved IT administration
- Encrypted stored credentials
- Administrative session timeout

**Treatment actions:**
- Strengthen privileged identity controls
- Monitor administrator authentication activity
- Review privileged access regularly
- Alert on suspicious administrative login attempts

**Treatment:** Mitigate  
**Target phase:** Identity & Access Management / Security Monitoring

---

### R-007 — Internal Network Reconnaissance

**Existing controls:**
- Departmental VLAN segmentation
- Inter-VLAN ACL restrictions
- Protected management and server networks

**Treatment actions:**
- Monitor unusual connection attempts
- Detect scanning behaviour
- Review network security logs
- Investigate repeated attempts to access restricted systems

**Treatment:** Mitigate  
**Target phase:** Security Monitoring & Detection

---

### R-008 — Vulnerable or Misconfigured Service

**Existing controls:**
- Network segmentation
- Restricted server exposure
- Network device hardening
- Unused switch ports disabled

**Treatment actions:**
- Introduce vulnerability scanning
- Prioritise vulnerabilities according to risk
- Establish patch-management procedures
- Validate remediation through rescanning

**Treatment:** Mitigate  
**Target phase:** Vulnerability Management

---

### R-009 — Security Control Misconfiguration

**Existing controls:**
- Configuration verification
- Connectivity testing
- Validation of permitted and denied traffic
- Documented network design

**Treatment actions:**
- Introduce formal change control
- Review security configurations following changes
- Maintain configuration documentation
- Periodically retest critical security controls

**Treatment:** Mitigate  
**Target phase:** Security Operations & Governance

---

### R-010 — Malicious Activity Goes Undetected

**Existing controls:**
- Preventive network security controls
- Network segmentation
- Restricted access paths
- Device hardening

**Treatment actions:**
- Centralise security logs
- Implement security monitoring
- Develop detection rules
- Establish alert-triage procedures
- Document investigation and escalation processes

**Treatment:** Mitigate  
**Target phase:** Security Monitoring & Detection

---

## Risk Register Review

The risk register will be updated as the KS Technologies environment develops.

When additional controls are implemented, risks will be reassessed to determine whether their likelihood or impact has been reduced. This allows the security program to demonstrate how technical and operational controls reduce organisational cybersecurity risk over time.
