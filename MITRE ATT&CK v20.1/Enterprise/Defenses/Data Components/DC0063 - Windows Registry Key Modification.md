# DC0063 - Windows Registry Key Modification

[Enterprise](../../README.md) / [Data Components](README.md)

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

- [AN0009 - Analytic 0009](../Analytics/AN0009.md)
- [AN0021 - Analytic 0021](../Analytics/AN0021.md)
- [AN0024 - Analytic 0024](../Analytics/AN0024.md)
- [AN0051 - Analytic 0051](../Analytics/AN0051.md)
- [AN0074 - Analytic 0074](../Analytics/AN0074.md)
- [AN0094 - Analytic 0094](../Analytics/AN0094.md)
- [AN0113 - Analytic 0113](../Analytics/AN0113.md)
- [AN0118 - Analytic 0118](../Analytics/AN0118.md)
- [AN0123 - Analytic 0123](../Analytics/AN0123.md)
- [AN0133 - Analytic 0133](../Analytics/AN0133.md)
- [AN0137 - Analytic 0137](../Analytics/AN0137.md)
- [AN0153 - Analytic 0153](../Analytics/AN0153.md)
- [AN0170 - Analytic 0170](../Analytics/AN0170.md)
- [AN0176 - Analytic 0176](../Analytics/AN0176.md)
- [AN0235 - Analytic 0235](../Analytics/AN0235.md)
- [AN0240 - Analytic 0240](../Analytics/AN0240.md)
- [AN0243 - Analytic 0243](../Analytics/AN0243.md)
- [AN0251 - Analytic 0251](../Analytics/AN0251.md)
- [AN0287 - Analytic 0287](../Analytics/AN0287.md)
- [AN0311 - Analytic 0311](../Analytics/AN0311.md)
- [AN0323 - Analytic 0323](../Analytics/AN0323.md)
- [AN0341 - Analytic 0341](../Analytics/AN0341.md)
- [AN0360 - Analytic 0360](../Analytics/AN0360.md)
- [AN0406 - Analytic 0406](../Analytics/AN0406.md)
- [AN0441 - Analytic 0441](../Analytics/AN0441.md)
- [AN0520 - Analytic 0520](../Analytics/AN0520.md)
- [AN0535 - Analytic 0535](../Analytics/AN0535.md)
- [AN0577 - Analytic 0577](../Analytics/AN0577.md)
- [AN0580 - Analytic 0580](../Analytics/AN0580.md)
- [AN0583 - Analytic 0583](../Analytics/AN0583.md)
- [AN0589 - Analytic 0589](../Analytics/AN0589.md)
- [AN0595 - Analytic 0595](../Analytics/AN0595.md)
- [AN0609 - Analytic 0609](../Analytics/AN0609.md)
- [AN0622 - Analytic 0622](../Analytics/AN0622.md)
- [AN0629 - Analytic 0629](../Analytics/AN0629.md)
- [AN0667 - Analytic 0667](../Analytics/AN0667.md)
- [AN0687 - Analytic 0687](../Analytics/AN0687.md)
- [AN0694 - Analytic 0694](../Analytics/AN0694.md)
- [AN0764 - Analytic 0764](../Analytics/AN0764.md)
- [AN0778 - Analytic 0778](../Analytics/AN0778.md)
- [AN0781 - Analytic 0781](../Analytics/AN0781.md)
- [AN0823 - Analytic 0823](../Analytics/AN0823.md)
- [AN0862 - Analytic 0862](../Analytics/AN0862.md)
- [AN0871 - Analytic 0871](../Analytics/AN0871.md)
- [AN0880 - Analytic 0880](../Analytics/AN0880.md)
- [AN0894 - Analytic 0894](../Analytics/AN0894.md)
- [AN0909 - Analytic 0909](../Analytics/AN0909.md)
- [AN0932 - Analytic 0932](../Analytics/AN0932.md)
- [AN0933 - Analytic 0933](../Analytics/AN0933.md)
- [AN0973 - Analytic 0973](../Analytics/AN0973.md)
- [AN0975 - Analytic 0975](../Analytics/AN0975.md)
- [AN0995 - Analytic 0995](../Analytics/AN0995.md)
- [AN1001 - Analytic 1001](../Analytics/AN1001.md)
- [AN1028 - Analytic 1028](../Analytics/AN1028.md)
- [AN1029 - Analytic 1029](../Analytics/AN1029.md)
- [AN1030 - Analytic 1030](../Analytics/AN1030.md)
- [AN1032 - Analytic 1032](../Analytics/AN1032.md)
- [AN1094 - Analytic 1094](../Analytics/AN1094.md)
- [AN1097 - Analytic 1097](../Analytics/AN1097.md)
- [AN1116 - Analytic 1116](../Analytics/AN1116.md)
- [AN1133 - Analytic 1133](../Analytics/AN1133.md)
- [AN1153 - Analytic 1153](../Analytics/AN1153.md)
- [AN1185 - Analytic 1185](../Analytics/AN1185.md)
- [AN1186 - Analytic 1186](../Analytics/AN1186.md)
- [AN1195 - Analytic 1195](../Analytics/AN1195.md)
- [AN1221 - Analytic 1221](../Analytics/AN1221.md)
- [AN1222 - Analytic 1222](../Analytics/AN1222.md)
- [AN1246 - Analytic 1246](../Analytics/AN1246.md)
- [AN1271 - Analytic 1271](../Analytics/AN1271.md)
- [AN1274 - Analytic 1274](../Analytics/AN1274.md)
- [AN1303 - Analytic 1303](../Analytics/AN1303.md)
- [AN1319 - Analytic 1319](../Analytics/AN1319.md)
- [AN1323 - Analytic 1323](../Analytics/AN1323.md)
- [AN1366 - Analytic 1366](../Analytics/AN1366.md)
- [AN1369 - Analytic 1369](../Analytics/AN1369.md)
- [AN1384 - Analytic 1384](../Analytics/AN1384.md)
- [AN1436 - Analytic 1436](../Analytics/AN1436.md)
- [AN1446 - Analytic 1446](../Analytics/AN1446.md)
- [AN1447 - Analytic 1447](../Analytics/AN1447.md)
- [AN1452 - Analytic 1452](../Analytics/AN1452.md)
- [AN1495 - Analytic 1495](../Analytics/AN1495.md)
- [AN1527 - Analytic 1527](../Analytics/AN1527.md)
- [AN1536 - Analytic 1536](../Analytics/AN1536.md)
- [AN1551 - Analytic 1551](../Analytics/AN1551.md)
- [AN1575 - Analytic 1575](../Analytics/AN1575.md)
- [AN1588 - Analytic 1588](../Analytics/AN1588.md)
- [AN1595 - Analytic 1595](../Analytics/AN1595.md)
- [AN1598 - Analytic 1598](../Analytics/AN1598.md)
- [AN2043 - Analytic 2043](../Analytics/AN2043.md)
