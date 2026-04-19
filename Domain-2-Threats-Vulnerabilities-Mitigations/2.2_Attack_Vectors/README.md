## 2.2 Threat Vectors and Attack Surfaces
 
A threat vector (also called an attack vector) is the method or pathway used to gain unauthorized access or deliver malicious content to a target. IT professionals must monitor known vectors and continuously look for new ones.
 
### Common Threat Vectors
 
| Vector | Description and Examples |
|---|---|
| Message-based | Email, SMS, and IM. Largest attack vector category. Malicious links, attachments, phishing, invoice scams, and social engineering. |
| Image-based | SVG files described in XML can embed HTML injection or JavaScript attack code. Difficult to identify visually. |
| File-based | Malicious code embedded in PDFs, ZIP/RAR archives, and Office documents with macros or add-ins. |
| Voice Call | Vishing (voice phishing), spam over IP, war dialing, and call tampering. |
| Removable Device | USB drives bypass firewalls entirely. Can contain malware, act as a keyboard (HID attack), or exfiltrate data. |
| Vulnerable Software | Client-based: infected installed software with known or unknown vulnerabilities. Agentless: server-side vulnerabilities affecting all users without a local agent. |
| Unsupported Systems | Unpatched, outdated OS or applications. A single unsupported system can be an entry point to the entire network. |
| Unsecure Networks | Wireless: outdated protocols (WEP, WPA), open or rogue access points. Wired: unmanaged switches, no 802.1X port authentication. Bluetooth: reconnaissance and implementation vulnerabilities. |
| Open Service Ports | Every open port is a potential entry point. Firewall rules must explicitly manage all port access. |
| Default Credentials | Factory default usernames and passwords provide full admin access. Must be changed on every device before deployment. |
| Supply Chain | Compromise at the manufacturer, vendor, or MSP level. Affects all downstream customers simultaneously. |
 
> Note on wired unsecure networks: wired networks without 802.1X port-based authentication allow any device physically connected to a switch port to access the network. This is frequently overlooked compared to wireless security but is equally relevant on the exam.
 
### Social Engineering Attacks
 
| Attack Type | How It Works |
|---|---|
| Phishing | Broad, untargeted social engineering via email. Malicious links, spoofed sender addresses, mismatched URLs, incorrect spelling and graphics. Sent to many recipients hoping some click. |
| Spear Phishing | Targeted phishing against a specific individual or organization. Uses personalized details (name, role, colleagues, recent events) to increase believability. Higher success rate than generic phishing. |
| Whaling | Spear phishing targeting senior executives (CEO, CFO, board members). The target's authority and access to finances or sensitive data is the asset being exploited. Often impersonates legal, financial, or regulatory bodies. |
| Vishing | Voice phishing. Fake security checks, voicemail-based attacks, eliciting information by phone. |
| Smishing | SMS phishing. Forwards malicious links or requests personal information via text message. |
| Business Email Compromise | Spoofed or compromised email accounts used for financial fraud (updated bank details) or malware delivery. Often follows spear phishing to establish initial trust. |
| Pretexting | Attacker fabricates a backstory to justify their request and gain trust before eliciting information. The story that makes the attack believable. |
| Typosquatting | Registers misspelled or similar domain names to redirect mistyped traffic to malicious sites. |
| Watering Hole | Attacker compromises a site the target group is known to visit, infecting all visitors passively. |
| Misinformation/Disinformation | Factually incorrect content used to influence public opinion. Often nation-state actors using social media, fake accounts, and paid advertising. |
| Brand Impersonation | Fake sites mimicking known brands. Delivers malware via popups, ads, or drive-by downloads. |
| Impersonation | Attacker pretends to be a person of authority using technical jargon and friendly rapport to elicit information. |
| Shoulder Surfing | Observing someone entering credentials, PINs, or sensitive data by looking over their shoulder or using a camera. Mitigate with privacy screens and positional awareness. |
| Tailgating / Piggybacking | Following an authorized person through a secured door without authenticating. Tailgating: the authorized person is unaware someone followed them. Piggybacking: the authorized person knowingly allows it. |
| Dumpster Diving | Searching discarded materials (printed documents, old drives, receipts) for sensitive information. Mitigated by clean desk policies, cross-cut shredding, and secure disposal bins. |
 
### Phishing Subtype Comparison
 
```
Phishing:       broad, untargeted > sent to many recipients > hopes someone clicks
Spear phishing: targeted at a specific person or org > uses personalized details > higher success rate
Whaling:        spear phishing targeting senior executives specifically > exploits their authority and financial access
```
 
The distinguishing factor on exam questions is always the level of targeting: broad vs. specific person vs. specific executive.
 
### Protecting Against Social Engineering
 
1. Never volunteer information or confirm details to an inbound caller
2. Always verify identity through a callback to a known number or third-party confirmation
3. Do not disclose personal or organizational details based on urgency or authority claims alone
4. Train users to recognize pretexting, urgency manipulation, and authority impersonation
5. Implement clean desk policies, shredding, and locked disposal bins to prevent dumpster diving
6. Deploy physical access controls and security cameras to deter tailgating
