# DC0079 - Driver Load

[Enterprise](../../README.md) / [Data Components](README.md)

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

- [AN0185 - Analytic 0185](../Analytics/AN0185.md)
- [AN0384 - Analytic 0384](../Analytics/AN0384.md)
- [AN0462 - Analytic 0462](../Analytics/AN0462.md)
- [AN0474 - Analytic 0474](../Analytics/AN0474.md)
- [AN0629 - Analytic 0629](../Analytics/AN0629.md)
- [AN0688 - Analytic 0688](../Analytics/AN0688.md)
- [AN0827 - Analytic 0827](../Analytics/AN0827.md)
- [AN0862 - Analytic 0862](../Analytics/AN0862.md)
- [AN0882 - Analytic 0882](../Analytics/AN0882.md)
- [AN0916 - Analytic 0916](../Analytics/AN0916.md)
- [AN0917 - Analytic 0917](../Analytics/AN0917.md)
- [AN1035 - Analytic 1035](../Analytics/AN1035.md)
- [AN1061 - Analytic 1061](../Analytics/AN1061.md)
- [AN1419 - Analytic 1419](../Analytics/AN1419.md)
- [AN1527 - Analytic 1527](../Analytics/AN1527.md)
- [AN2038 - Analytic 2038](../Analytics/AN2038.md)
