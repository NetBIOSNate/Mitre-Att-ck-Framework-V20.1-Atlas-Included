# T1059.008 - Network Device CLI

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1059 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse scripting or built-in command line interpreters (CLI) on network devices to execute malicious command and payloads. The CLI is the primary means through which users and administrators interact with the device in order to view system information, modify device operations, or perform diagnostic and administrative functions. CLIs typically contain various permission levels required for different commands. 

Scripting interpreters automate tasks and extend functionality beyond the command set included in the network OS. The CLI and scripting interpreter are accessible through a direct console connection, or through remote means, such as telnet or [SSH](https://attack.mitre.org/techniques/T1021/004).

Adversaries can use the network CLI to change how network devices behave and operate. The CLI may be used to manipulate traffic flows to intercept or manipulate data, modify startup configuration parameters to load malicious system software, or to disable security features or logging to avoid detection.(Citation: Cisco Synful Knock Evolution)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1059/008)

**Tactics**  [Execution](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries leveraged the native CLI of the targeted FortiGate device.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S9013 - DRYHOOK](../../../../Threat%20Intelligence/Software/Malware/S9013%20-%20DRYHOOK.md) — [DRYHOOK](https://attack.mitre.org/software/S9013) has the ability to interact with Ivanti Connect Secure environments and to modify system components.(Citation: Google UNC5221 Ivanti January 2025)(Citation: Picus Security UNC5221 Ivanti May 2025) [Google UNC5221 Ivanti January 2025](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day) · [Picus Security UNC5221 Ivanti May 2025](https://www.picussecurity.com/resource/blog/unc5221-cve-2025-22457-ivanti-connect-secure)
- [S1186 - Line Dancer](../../../../Threat%20Intelligence/Software/Malware/S1186%20-%20Line%20Dancer.md) — [Line Dancer](https://attack.mitre.org/software/S1186) can execute native commands in networking device command line interfaces.(Citation: Cisco ArcaneDoor 2024)(Citation: CCCS ArcaneDoor 2024) [CCCS ArcaneDoor 2024](https://www.cyber.gc.ca/en/news-events/cyber-activity-impacting-cisco-asa-vpns) · [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [S9014 - PHASEJAM](../../../../Threat%20Intelligence/Software/Malware/S9014%20-%20PHASEJAM.md) — [PHASEJAM](https://attack.mitre.org/software/S9014) has leveraged native commands associated with the compromised network appliance to execute code.(Citation: Google UNC5221 Ivanti January 2025) [Google UNC5221 Ivanti January 2025](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day)
- [C0056 - RedPenguin](../../../../Threat%20Intelligence/Campaigns/C0056%20-%20RedPenguin.md) — During [RedPenguin](https://attack.mitre.org/campaigns/C0056), [UNC3886](https://attack.mitre.org/groups/G1048) accessed the Junos OS CLI on targeted devices.(Citation: Mandiant UNC3886 Juniper Routers MAR 2025)(Citation: Juniper RedPenguin MAR 2025) [Juniper RedPenguin MAR 2025](https://supportportal.juniper.net/sfc/servlet.shepherd/document/download/069Dp00000FzdmIIAR?operationContext=S1) · [Mandiant UNC3886 Juniper Routers MAR 2025](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-targets-juniper-routers)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has executed commands on network devices using the native command line interface.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [Salt Typhoon](https://attack.mitre.org/groups/G1045) has leveraged Tcl scripts on Cisco IOS devices to include `TCLprox.tcl` and `map.tcl` when `tclsh` was available.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [Salt Typhoon](https://attack.mitre.org/groups/G1045) also leveraged TACACS+ and RADIUS to modify victim network devices.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — TACACS+ can keep control over which commands administrators are permitted to use through the configuration of authentication and command authorization. (Citation: Cisco IOS Software Integrity Assurance - TACACS) [Cisco IOS Software Integrity Assurance - TACACS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#39)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Use of Authentication, Authorization, and Accounting (AAA) systems will limit actions administrators can perform and provide a history of user actions to detect unauthorized use and abuse. TACACS+ can keep control over which commands administrators are permitted to use through the configuration of authentication and command authorization(Citation: Cisco IOS Software Integrity Assurance - AAA) (Citation: Cisco IOS Software Integrity Assurance - TACACS) [Cisco IOS Software Integrity Assurance - AAA](https://tools.cisco.com/security/center/resources/integrity_assurance.html#38) · [Cisco IOS Software Integrity Assurance - TACACS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#39)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Use of Authentication, Authorization, and Accounting (AAA) systems will limit actions users can perform and provide a history of user actions to detect unauthorized use and abuse. Ensure least privilege principles are applied to user accounts and groups so that only authorized users can perform configuration changes. (Citation: Cisco IOS Software Integrity Assurance - AAA) [Cisco IOS Software Integrity Assurance - AAA](https://tools.cisco.com/security/center/resources/integrity_assurance.html#38)

## Detection strategies

- [DET0142 - Behavioral Detection of CLI Abuse on Network Devices](../../../../Defenses/Detection%20Strategies/DET0142%20-%20Behavioral%20Detection%20of%20CLI%20Abuse%20on%20Network%20Devices.md)

## Sources

- [Cisco IOS Software Integrity Assurance - Command History](https://tools.cisco.com/security/center/resources/integrity_assurance.html#23)
- [Cisco Synful Knock Evolution](https://blogs.cisco.com/security/evolution-of-attacks-on-cisco-ios-devices)
