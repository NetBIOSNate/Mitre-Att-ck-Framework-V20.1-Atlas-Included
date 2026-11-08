# DC0102 - Network Share Access

[ICS](../../README.md) / [Data Components](README.md)

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

- [AN1878 - Analytic 1878](../Analytics/AN1878.md)
- [AN1886 - Analytic 1886](../Analytics/AN1886.md)
