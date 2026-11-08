# DC0071 - Active Directory Object Access

[Enterprise](../../README.md) / [Data Components](README.md)

Object access refers to activities where AD objects (e.g., user accounts, groups, policies) are accessed or queried. Example: Windows Event ID 4661 logs object access attempts. Examples:

- Attribute Access: e.g., `userPassword`, `memberOf`, `securityDescriptor`.
- Group Enumeration: Enumerating critical group members (e.g., Domain Admins).
- User Attributes: Commonly accessed attributes like `samAccountName`, `lastLogonTimestamp`.
- Policy Access: Accessing GPOs to understand security settings.

*Data Collection Measures:*

- Audit Policies:
    - Enable "Audit Directory Service Access" under Advanced Audit Policies (Success and Failure).
    - Path: `Computer Configuration > Policies > Windows Settings > Security Settings > Advanced Audit Policy Configuration > Audit Policies > Object AccessEnable: Audit Directory Service Access` (Success and Failure).
    - Captured Events: IDs 4661, 4662.
- Event Forwarding: Use WEF to centralize logs for SIEM analysis.
- SIEM Integration: Collect and parse logs (e.g., 4661, 4662) using tools like Splunk or Azure Sentinel.
- Log Filtering:
- Focus on sensitive objects/attributes like:
    - `Domain Admins` group.
    - `userPassword`, `ntSecurityDescriptor`.
- Enable EDR Monitoring:
    - Detect processes accessing sensitive AD objects (e.g., samAccountName, securityDescriptor).
    - Log all attempts to enumerate critical groups (e.g., "Domain Admins").

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0071)

## Log sources and channels

- **WinEventLog:Security** — EventCode=4662
- **WinEventLog:Security** — EventCode=4661

## Analytics using this component

- [AN0016 - Analytic 0016](../Analytics/AN0016.md)
- [AN0152 - Analytic 0152](../Analytics/AN0152.md)
- [AN0455 - Analytic 0455](../Analytics/AN0455.md)
- [AN0648 - Analytic 0648](../Analytics/AN0648.md)
- [AN0770 - Analytic 0770](../Analytics/AN0770.md)
- [AN1632 - Analytic 1632](../Analytics/AN1632.md)
