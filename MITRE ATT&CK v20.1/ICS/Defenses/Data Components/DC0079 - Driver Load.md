# DC0079 - Driver Load

[ICS](../../README.md) / [Data Components](README.md)

The process of attaching a driver, which is a software component that allows the operating system and applications to interact with hardware devices, to either user-mode or kernel-mode of a system. This can include benign actions (e.g., hardware drivers) or malicious behavior (e.g., rootkits or unsigned drivers). Examples: 

- Legitimate Driver Loading: A new graphics driver from a vendor like NVIDIA or AMD is loaded into the system.
- Unsigned Driver Loading: A driver without a valid digital signature is loaded into the kernel.
- Rootkit Installation: A malicious rootkit driver is loaded to manipulate kernel-mode processes.
- Anti-Virus or EDR Driver Loading: An Endpoint Detection and Response (EDR) solution loads its driver to monitor system activities.
- Driver Misuse: A legitimate driver is loaded and exploited to execute malicious actions, such as using vulnerable drivers for bypassing defenses (e.g., Bring Your Own Vulnerable Driver (BYOVD) attacks).

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0079)

## Log sources and channels

- **linux:syslog** — dmesg or syslog for module loads
- **linux:syslog** — Driver load events or firmware load failures for hardware devices
- **WinEventLog:Sysmon** — EventCode=6
- **WinEventLog:Sysmon** — EventCode=6 kernel driver load from path not in trusted driver paths, not signed by trusted signer list
- **WinEventLog:Sysmon** — EventCode=6 of a known vulnerable third-party driver immediately preceding privilege escalation indicators
- **WinEventLog:Sysmon** — EventCode=6 for wireless capture driver on host not in designated wireless management station list
- **WinEventLog:Sysmon** — EventCode= 6 Npcap/WinPcap driver loaded by image not in authorized capture software

## Analytics using this component

- [AN1932 - Analytic 1932](../Analytics/AN1932.md)
- [AN2167 - Analytic 2167](../Analytics/AN2167.md)
- [AN2261 - Analytic 2261](../Analytics/AN2261.md)
- [AN2269 - Analytic 2269](../Analytics/AN2269.md)
- [AN2272 - Analytic 2272](../Analytics/AN2272.md)
