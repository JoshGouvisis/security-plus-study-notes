## 1.3 - Change Management

A formal process for controlling modifications to systems, configurations, and software. Prevents unplanned downtime, security misconfigurations, and cascading failures.

### Change Approval Process

1. Submit request form: purpose, scope, affected systems, risk level
2. Identify owner: business unit responsible, separate from the technician performing the change
3. Identify stakeholders: all parties impacted by the change
4. Conduct impact analysis: risk value (high/medium/low), risk of NOT making the change
5. Test in sandbox: isolated from production systems
6. Obtain Change Control Board approval
7. Define and document backout plan
8. Schedule maintenance window
9. Obtain end-user acceptance after completion

### Key Business Process Elements

| Element | Description |
|---|---|
| Ownership | The business unit owns the change process. IT executes it. These are separate roles. |
| Stakeholders | All parties impacted. A label printer upgrade can affect shipping, accounting, revenue reporting, and executive visibility. |
| Impact Analysis | Risk of making the change AND risk of not making the change (security vulnerabilities, unplanned downtime). |
| Test Results | Sandbox testing validates behavior before production deployment. Cannot replicate every production scenario. |
| Backout Plan | A documented, tested rollback procedure. Not all changes are easily reversible. Always maintain current backups. |
| Maintenance Window | Scheduled execution time. Retail and 24/7 environments have specific scheduling constraints. |
| Standard Operating Procedure | Change management policy must be documented, accessible, and updated as the process evolves. |

### Technical Change Considerations

| Consideration | Notes |
|---|---|
| Allow List | Only pre-approved applications may execute. Most restrictive approach. |
| Deny List | Blocks known-bad applications. Used by antivirus and anti-malware. |
| Restricted Activities | Change approval authorizes a specific change, not all changes within the window. |
| Downtime | Plan for service unavailability. Use secondary systems during upgrades. Automate switchback. |
| Restarts | Document all required reboots, service restarts, and application relaunches. |
| Legacy Applications | No longer vendor-supported. The organization becomes its own support team. Requires dedicated documentation. |
| Dependencies | Changes to one component may require changes to others. Upgrade order matters (e.g., firewall firmware before management software). |
| Documentation | Update network diagrams and policy documents with every change. Outdated documentation is a security risk. |
| Version Control | Tracks configuration state over time. Enables rollback to a prior known-good configuration. |
