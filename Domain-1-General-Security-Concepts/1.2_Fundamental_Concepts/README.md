## 1.2 - Fundamental Security Concepts

### CIA Triad

The three foundational principles of information security. Every security decision maps to one or more of these.

| Principle | Definition | Controls |
|---|---|---|
| Confidentiality | Information accessible only to authorized individuals | Encryption, access controls, MFA |
| Integrity | Data stored and transmitted exactly as intended; any modification is detectable | Hashing, digital signatures, certificates |
| Availability | Authorized users can access systems and data when needed | Redundancy, fault tolerance, patching |

### Non-Repudiation

Provides cryptographic proof that a message came from a specific sender and was not altered.

| Component | Mechanism | What It Proves |
|---|---|---|
| Proof of integrity | Hash of the data | The data has not changed |
| Proof of origin | Digital signature created with sender's private key | The message came from a specific sender |

A hash alone proves integrity but does not identify the sender. A digital signature proves both. Non-repudiation requires both.

### AAA Framework

| Element | Definition |
|---|---|
| Identification | Who you claim to be, typically a username |
| Authentication | Proving the claim using passwords, certificates, biometrics, or tokens |
| Authorization | What you are permitted to access based on your verified identity |
| Accounting | Logging what you did: login time, data accessed, resources used, logout time |

#### Authenticating Devices

Devices authenticate using digitally signed certificates issued by a trusted internal Certificate Authority (CA). Business processes such as VPN access and network admission control rely on device certificates.

Device presents certificate > CA signature verified > access granted

### Authorization Models

| Approach | Description |
|---|---|
| No abstraction | Direct user-to-resource mapping. Simple but does not scale. |
| With abstraction | Roles, organizations, or attributes define access rights. Reduces administrative complexity. |
| Common models | RBAC (role-based), ABAC (attribute-based), MAC (mandatory) |

### Gap Analysis

A structured process to identify the difference between the current security posture and a defined target baseline.

1. Select a framework target: NIST SP 800-171, ISO/IEC 27001, or internal standard
2. Evaluate people: training, certifications, policy knowledge
3. Evaluate processes: existing IT systems and current security policies
4. Compare current state to baseline: identify specific gaps
5. Produce a report: current state, gaps identified, and remediation path with time and cost

### Zero Trust

Eliminates implicit trust for anything inside the network perimeter. Every device, user, and connection must be verified regardless of location.

#### Planes of Operation

| Plane | Function |
|---|---|
| Data Plane | Processes frames, packets, and network data. Handles forwarding, encryption, trunking, and NAT. |
| Control Plane | Manages the data plane. Defines policies, maintains routing/session/NAT tables. |

#### Zero Trust Components

| Component | Role |
|---|---|
| Adaptive Identity | Evaluates context at request time: location, device type, IP address, relationship to organization |
| Threat Scope Reduction | Minimizes the number of possible entry points into the environment |
| Policy-driven Access Control | Combines adaptive identity with predefined rules |
| Policy Enforcement Point (PEP) | The gatekeeper. Allows, monitors, or terminates connections. |
| Policy Engine | Evaluates access requests against policy and threat intelligence |
| Policy Administrator | Communicates decisions to the PEP. Issues or revokes access tokens. |

Security zones categorize traffic by trust level (internal, external, VPN, HR, IT, Accounting). Even trusted-to-trusted zone transitions require verification in a Zero Trust model.

### Physical Security

#### Barriers and Access Controls

| Control | Function |
|---|---|
| Bollards | Block vehicle access while allowing pedestrian movement |
| Access Control Vestibule | Interlocking door system. Only one door open at a time. Prevents tailgating. |
| Fencing | Defines perimeter. Can be opaque or transparent, reinforced, and topped with razor wire. |

#### Surveillance and Detection

| Control | Notes |
|---|---|
| CCTV | Networked cameras with motion detection, license plate recognition, and facial recognition |
| Security Guards | Physical protection, identity validation, two-person integrity rules |
| Access Badges | Photo ID with electronic logging. Required to be worn at all times. |
| Lighting | Increases deterrence. IR cameras require careful angle design to avoid shadows. |

#### Sensors

| Type | Detection Method |
|---|---|
| Infrared | Detects heat signatures in light and dark conditions |
| Pressure | Detects force changes in floors and windows |
| Microwave | Detects movement across large open areas |
| Ultrasonic | Emits sound waves and detects returning signals to identify motion |

### Deception and Disruption Technology

| Mechanism | Description |
|---|---|
| Honeypot | A single decoy system designed to attract and trap attackers |
| Honeynet | Multiple connected honeypots forming a decoy network (servers, routers, firewalls, workstations) |
| Honeyfile | A decoy file such as passwords.txt that triggers an alert when accessed |
| Honeytoken | Traceable fake data (API keys, email addresses, DB records) that alerts when used |
