# DC0102 - Network Share Access

[Enterprise](../../README.md) / [Data Components](README.md)

Opening a network share, which makes the contents available to the requestor (ex: Windows EID 5140 or 5145)

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0102)

## Log sources and channels

- **Network Share** — None
- **WinEventLog:Microsoft-Windows-SMBClient/Security** — EventCode=31001
- **WinEventLog:Security** — EventCode=5140
- **WinEventLog:Security** — EventCode=5145
- **WinEventLog:Microsoft-Windows-SMBServer** — Access to SYSVOL share from non-admin user or unusual endpoints
- **NSM:Flow** — smb_files.log
- **m365:unified** — FileUploaded, FileAccessed
- **fileserver:audit** — sequential access to above bulk document access threshold files within information repository time window from single session
- **WinEventLog:Security** — Windows Security Event ID 5140/5145: EventCode=5145 for file write to Industrial Control Systems (ICS) host, source not in authorized file sources

## Analytics using this component

- [AN0194 - Analytic 0194](../Analytics/AN0194.md)
- [AN0516 - Analytic 0516](../Analytics/AN0516.md)
- [AN1034 - Analytic 1034](../Analytics/AN1034.md)
- [AN1075 - Analytic 1075](../Analytics/AN1075.md)
- [AN1145 - Analytic 1145](../Analytics/AN1145.md)
- [AN1160 - Analytic 1160](../Analytics/AN1160.md)
- [AN1298 - Analytic 1298](../Analytics/AN1298.md)
- [AN1299 - Analytic 1299](../Analytics/AN1299.md)
- [AN1301 - Analytic 1301](../Analytics/AN1301.md)
- [AN1309 - Analytic 1309](../Analytics/AN1309.md)
- [AN1516 - Analytic 1516](../Analytics/AN1516.md)
