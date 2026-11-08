# DC0045 - Windows Registry Key Deletion

[ICS](../../README.md) / [Data Components](README.md)

The removal of a registry key within the Windows operating system.

*Data Collection Measures:*

- Windows Event Logs
    - Event ID 4658 - Registry Key Handle Closed: Captures when a handle to a registry key is closed, which may indicate deletion.
    - Event ID 4660 - Object Deleted: Logs when a registry key is deleted.
- Sysmon (System Monitor) for Windows
    - Sysmon Event ID 12 - Registry Key Deleted: Logs when a registry key is removed.
    - Sysmon Event ID 13 - Registry Value Deleted: Captures removal of specific registry values.
- Endpoint Detection and Response (EDR) Solutions
    - Monitor registry deletions for suspicious behavior.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0045)

## Log sources and channels

- **Windows Registry** — None
