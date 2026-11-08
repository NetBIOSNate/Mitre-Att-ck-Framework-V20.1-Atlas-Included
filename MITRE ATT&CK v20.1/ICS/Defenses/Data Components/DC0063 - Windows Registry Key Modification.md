# DC0063 - Windows Registry Key Modification

[ICS](../../README.md) / [Data Components](README.md)

Changes made to an existing registry key or its values. These modifications can include altering permissions, modifying stored data, or updating configuration settings.

*Data Collection Measures:*

- Windows Event Logs
    - Event ID 4657 - Registry Value Modified: Logs changes to registry values, including modifications to startup entries, security settings, or system configurations.
- Sysmon (System Monitor) for Windows
    - Sysmon Event ID 13 - Registry Value Set: Captures changes to specific registry values.
    - Sysmon Event ID 14 - Registry Key & Value Renamed: Logs renaming of registry keys, which may indicate evasion attempts.
- Endpoint Detection and Response (EDR) Solutions
    - Monitor registry modifications for suspicious behavior.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0063)

## Log sources and channels

- **WinEventLog:Security** — EventCode=4657
- **WinEventLog:Security** — EventCode=4663, 4670, 4656
- **WinEventLog:Sysmon** — StubPath value written under HKLM\SOFTWARE\Microsoft\Active Setup\Installed Components
- **m365:unified** — MacroSecuritySettingsChanged or SafeModeDisabled
- **WinEventLog:Sysmon** — EventCode=13, 14
- **WinEventLog:Security** — modification to Winlogon registry keys such as Shell, Notify, or Userinit
- **WinEventLog:Security** — Registry key modification HKLM\Software\Policies\Microsoft\Windows NT\DNSClient\EnableMulticast
- **macos:unifiedlog** — g_CiOptions modification or SIP state change
- **WinEventLog:Sysmon** — Autoruns reports DLLs in AppInit_DLLs key
- **opc:applog** — Open Platform Communications (OPC) server data change notification or value write from client_id not matching authorized data acquisition service
- **WinEventLog:Sysmon** — EventCode=13 to Communication (COM) port configuration key by process not in authorized serial port management tools

## Analytics using this component

- [AN1879 - Analytic 1879](../Analytics/AN1879.md)
- [AN2280 - Analytic 2280](../Analytics/AN2280.md)
