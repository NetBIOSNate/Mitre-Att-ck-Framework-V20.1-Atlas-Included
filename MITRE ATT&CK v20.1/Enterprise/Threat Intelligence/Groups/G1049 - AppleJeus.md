# G1049 - AppleJeus

[Enterprise](../../README.md) / [Groups](README.md)

[AppleJeus](https://attack.mitre.org/groups/G1049) is a North Korean state-sponsored threat group attributed to the Reconnaissance General Bureau. Associated with the broader [Lazarus Group](https://attack.mitre.org/groups/G0032) umbrella of actors, [AppleJeus](https://attack.mitre.org/groups/G1049) has been active since at least 2018 and is closely aligned in resources with TEMP.hermit, another DPRK-affiliated group under the same umbrella.(Citation: dtex DPRK 2025 structure ITworkers) The group’s primary mission is to generate and launder revenue to provide financial support to the government. [AppleJeus](https://attack.mitre.org/groups/G1049) primarily targets the cryptocurrency industry and is most notably responsible for the [3CX Supply Chain Attack](https://attack.mitre.org/campaigns/C0057).(Citation: Mandiant 3cx UNC4736 2023) The group traditionally deploys malicious cryptocurrency software in combination with [Phishing](https://attack.mitre.org/techniques/T1566). From these compromised environments, it selectively deploys additional backdoors to enable extended operations against high-value financial targets.(Citation: Mandiant DPRK Groups 2023)(Citation: JPCert Blog Laz Subgroups 2025)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1049)

## Aliases

- Gleaming Pisces
- Citrine Sleet
- UNC1720
- UNC4736

## Techniques used

- [T1657 - Financial Theft](../../Tactics/15%20TA0040%20-%20Impact/T1657%20-%20Financial%20Theft/README.md)
- [T1566 - Phishing](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/README.md)

## Attributed campaigns

- [C0057 - 3CX Supply Chain Attack](../Campaigns/C0057%20-%203CX%20Supply%20Chain%20Attack.md)

## Sources

- [Mandiant 3cx UNC4736 2023](https://cloud.google.com/blog/topics/threat-intelligence/3cx-software-supply-chain-compromise/)
- [dtex DPRK 2025 structure ITworkers](https://reports.dtexsystems.com/DTEX-Exposing+DPRK+Cyber+Syndicate+and+Hidden+IT+Workforce.pdf)
- [Mandiant DPRK Groups 2023](https://cloud.google.com/blog/topics/threat-intelligence/north-korea-cyber-structure-alignment-2023)
- [Unit42 DPRK Threat Groups 2024](https://unit42.paloaltonetworks.com/threat-assessment-north-korean-threat-groups-2024/)
- [JPCert Blog Laz Subgroups 2025](https://blogs.jpcert.or.jp/en/2025/03/classifying-lazaruss-subgroup.html)
