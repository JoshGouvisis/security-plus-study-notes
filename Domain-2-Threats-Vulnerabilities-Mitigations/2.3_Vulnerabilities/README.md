## 2.3 Types of Vulnerabilities
 
| Vulnerability | Description |
|---|---|
| Memory Injection | Malware injects itself into a legitimate running process, inheriting its rights and permissions. DLL injection is the most common form. |
| Buffer Overflow | Attacker writes data beyond the allocated buffer, overwriting adjacent memory including return addresses. Redirects code execution to attacker-controlled payload. Repeatable once crafted. |
| Race Condition (TOCTOU) | Two events occur simultaneously within an application. Time-of-Check to Time-of-Use: resource is verified safe, then changed before it is actually used. |
| Malicious Update | A legitimate software update mechanism is compromised to deliver malicious code. Applies to auto-updates, manual downloads, and third-party updaters. |
| OS Vulnerabilities | Every OS has unknown vulnerabilities. Requires regular patching, pre-deployment testing, and maintained backups. |
| SQLi | Attacker injects SQL commands through input fields. Can view, modify, or delete entire database contents. |
| XSS Reflected | Script embedded in a crafted URL executes in the victim's browser when they click the link. Non-persistent. Targets one specific victim. |
| XSS Stored | Malicious script posted to a site executes in every visitor's browser automatically. Persistent. Wider blast radius than reflected. |
| Hardware/Firmware | IoT and embedded device OS-level vulnerabilities. Only the vendor can issue fixes. |
| End-of-Life (EOL/EOSL) | EOL: manufacturer stops selling. EOSL: no more security patches. Requires compensating controls such as additional firewall rules or IPS signatures. |
| VM Escape | Attacker breaks out of a guest VM to access the hypervisor or other VMs on the same host. |
| Resource Reuse | Hypervisor reallocates physical memory or storage without fully wiping it. Data residue from one VM may be accessible to another. |
| Cloud Misconfiguration | Incorrect permissions, missing MFA on management consoles, unpatched critical vulnerabilities (CVSS 7.0+). |
| Supply Chain | Compromise at any point in the chain (service, hardware, or software provider) affects all downstream users simultaneously. |
| Misconfiguration | Open permissions, unsecured admin accounts, insecure protocols (Telnet, FTP, SMTP, IMAP), default credentials, unnecessary open ports. |
| Mobile: Sideloading | Apps installed outside the official app store bypass store vetting and MDM policy enforcement. |
| Mobile: Jailbreaking/Rooting | Removes OS restrictions. Bypasses MDM. Allows unauthorized firmware installation. Android: rooting. iOS: jailbreaking. |
| Zero-Day | Unknown to the vendor. No patch exists. Race between attacker exploitation and vendor discovery and patching. |
 
### Buffer Overflow Mechanics
 
```
1. Application allocates a fixed-size buffer for input (e.g., 256 bytes)
2. Attacker sends more data than the buffer can hold
3. Overflow overwrites adjacent memory, including the return address on the stack
4. Attacker crafts payload to redirect execution to their own code
5. Exploit is fully repeatable once successfully developed
```
 
Defenses: input validation, bounds checking, ASLR (Address Space Layout Randomization), stack canaries.
 
### XSS: Stored vs. Reflected
 
| Type | Persistence | Trigger | Blast Radius |
|---|---|---|---|
| Reflected (Non-persistent) | Not stored on server | Victim clicks a crafted link | One victim per link |
| Stored (Persistent) | Written to server storage | Automatic on page load | Every visitor to the page |
