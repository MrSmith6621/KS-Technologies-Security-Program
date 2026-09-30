# KS Technologies — Threat Model

## Purpose

This threat model identifies realistic threats that could affect the KS Technologies environment and evaluates how the current and planned security controls reduce those threats.

The model assumes that no individual security control is completely effective. An attacker may gain access to a user account or endpoint, so the environment should limit what can be accessed after an initial compromise.

The threat model will also guide later phases of the security program, particularly security monitoring, identity and access management, vulnerability management, and incident response.

---

## Environment in Scope

The current KS Technologies environment includes:

- IT
- Finance
- HR
- Sales
- Operations
- Management
- Guest network
- Server infrastructure
- Network management infrastructure
- Privileged IT administration

The environment is segmented using dedicated VLANs with inter-VLAN communication controlled through ACLs.

---

## Primary Threat Actors

### External Attacker

An attacker outside KS Technologies may attempt to gain initial access through phishing, credential theft, vulnerable services, or other exposed systems.

Potential objectives include:

- Credential theft
- Data theft
- Malware deployment
- Lateral movement
- Privilege escalation
- Disruption of business services

---

### Compromised Employee

A legitimate employee account or endpoint may become compromised through phishing, malware, credential theft, or another attack.

The attacker may then attempt to use the employee's existing network access to reach additional systems.

This is considered one of the primary threats to the environment.

---

### Malicious Insider

An employee or contractor with legitimate access may intentionally attempt to access information or systems outside their authorised responsibilities.

Network and identity controls should limit the amount of access available to any individual user.

---

### Untrusted Guest Device

Devices connected to the guest network are not managed by KS Technologies.

They may be:

- Infected with malware
- Misconfigured
- Controlled by an attacker
- Intentionally used to probe internal systems

Guest devices are therefore treated as untrusted.

---

## Threat Scenarios

### T-001 — Phishing and Credential Theft

**Scenario:**

An employee receives a phishing message and submits their credentials to an attacker-controlled service.

The attacker obtains valid KS Technologies credentials and attempts to access company resources.

**Potential impact:**

- Account compromise
- Unauthorised access
- Data exposure
- Further credential theft
- Lateral movement

**Current mitigation:**

- Network segmentation limits the systems reachable from individual departments.
- ACLs restrict unnecessary cross-department communication.

**Remaining exposure:**

Identity-specific protections and authentication monitoring have not yet been implemented.

**Planned controls:**

- Identity and Access Management
- Authentication monitoring
- Security alerting
- Incident response procedures

---

### T-002 — Compromised Endpoint and Lateral Movement

**Scenario:**

An attacker gains control of an employee workstation and attempts to move from the compromised VLAN into other departments or critical infrastructure.

Example attack path:

```text
Phishing
   ↓
Employee Endpoint Compromised
   ↓
Attacker Gains Network Access
   ↓
Attempts Lateral Movement
   ↓
HR / Finance / Servers / Management
   ↓
Network Segmentation and ACL Enforcement
```

**Potential impact:**

- Compromise of additional endpoints
- Sensitive data exposure
- Privilege escalation
- Increased attack blast radius

**Current mitigation:**

- Departmental VLAN segmentation
- Inter-VLAN ACLs
- Dedicated server VLAN
- Dedicated management VLAN
- Restricted privileged administration

**Remaining exposure:**

Permitted traffic could still be abused and suspicious activity is not yet centrally monitored.

**Planned controls:**

- Centralised logging
- Detection rules
- Endpoint monitoring
- Incident investigation

---

### T-003 — Unauthorised HR or Finance Access

**Scenario:**

A user from another department attempts to access systems belonging to HR or Finance.

**Potential impact:**

- Exposure of sensitive employee information
- Exposure of financial information
- Privacy breach
- Business and reputational impact

**Current mitigation:**

- HR and Finance operate in separate VLANs.
- ACLs prevent unnecessary communication between the departments.
- Access controls were tested to verify prohibited traffic was blocked.

**Remaining exposure:**

Compromised authorised accounts may still provide access to sensitive information.

**Planned controls:**

- Role-based access control
- Identity monitoring
- Access reviews
- Security logging

---

### T-004 — Guest Network Access to Corporate Resources

**Scenario:**

A malicious or compromised guest device attempts to discover or communicate with KS Technologies internal systems.

**Potential impact:**

- Internal reconnaissance
- Exploitation attempts
- Unauthorised access
- Malware propagation

**Current mitigation:**

- Guest devices operate on dedicated VLAN 70.
- Guest ACLs prevent communication with corporate VLANs.
- Isolation was validated through connectivity testing.

**Remaining exposure:**

Repeated or suspicious blocked connection attempts are not currently centrally monitored.

**Planned controls:**

- Network-event monitoring
- Detection of suspicious connection attempts
- Centralised logging

---

### T-005 — Unauthorised Server Access

**Scenario:**

A standard employee or compromised endpoint attempts to reach systems within the protected server VLAN.

**Potential impact:**

- Data theft
- Server compromise
- Service disruption
- Malware or ransomware deployment

**Current mitigation:**

- Dedicated Server VLAN 80
- ACL-based server restrictions
- IT administrative separation
- Finance limited to required service-level access

**Remaining exposure:**

Permitted services could contain vulnerabilities or be abused using compromised credentials.

**Planned controls:**

- Vulnerability scanning
- Server monitoring
- Authentication monitoring
- Patch and remediation processes

---

### T-006 — Network Administrator Account Compromise

**Scenario:**

An attacker obtains privileged network administrator credentials and attempts to access routers or switches.

**Potential impact:**

- Network configuration changes
- Security control bypass
- Traffic interception
- Loss of network availability
- Wider infrastructure compromise

**Current mitigation:**

- SSH version 2
- Telnet disabled
- Dedicated management VLAN
- Management access restricted to approved IT administration
- Encrypted stored credentials
- Session timeout

**Remaining exposure:**

Local credentials remain a high-value target.

**Planned controls:**

- Stronger identity controls
- Privileged access management
- Administrative activity monitoring
- Authentication alerting

---

### T-007 — Network Reconnaissance

**Scenario:**

An attacker with access to a workstation attempts to identify hosts, services, network ranges, or management systems.

**Potential impact:**

Reconnaissance may provide information required for:

- Lateral movement
- Service exploitation
- Privilege escalation
- Target selection

**Current mitigation:**

Network segmentation and ACLs reduce the number of reachable systems from each VLAN.

**Remaining exposure:**

Reconnaissance within permitted network boundaries may still occur.

**Planned controls:**

- Security monitoring
- Detection of unusual network activity
- Vulnerability management

---

### T-008 — Vulnerable or Misconfigured Service

**Scenario:**

A server, endpoint, or network service contains a known vulnerability or insecure configuration that could be exploited.

**Potential impact:**

- Remote system compromise
- Privilege escalation
- Data exposure
- Service disruption

**Current mitigation:**

- Network segmentation
- Restricted server exposure
- Network device hardening

**Remaining exposure:**

No formal vulnerability management process has yet been implemented.

**Planned controls:**

- Vulnerability scanning
- Risk-based remediation
- Patch management
- Remediation validation

---

### T-009 — Misconfiguration of Security Controls

**Scenario:**

An incorrect ACL, VLAN assignment, switch configuration, or administrative change unintentionally exposes systems.

**Potential impact:**

- Security control bypass
- Unauthorised connectivity
- Exposure of sensitive systems
- Business disruption

**Current mitigation:**

- Configuration verification
- Connectivity testing
- Both permitted and denied traffic tested during implementation

**Remaining exposure:**

Future changes could introduce configuration errors.

**Planned controls:**

- Change-control process
- Configuration review
- Continuous monitoring
- Periodic security validation

---

### T-010 — Security Activity Goes Undetected

**Scenario:**

An attacker performs suspicious authentication, reconnaissance, lateral movement, or access attempts without generating a security response.

**Potential impact:**

- Increased attacker dwell time
- Further compromise
- Delayed containment
- Larger incident impact

**Current mitigation:**

Preventive controls currently reduce available attack paths.

**Remaining exposure:**

The environment does not yet have centralised security monitoring and detection.

**Planned controls:**

- Centralised logging
- Security monitoring
- Detection rules
- Alert triage
- Investigation procedures

**Planned phase:** Security Monitoring & Detection

---
