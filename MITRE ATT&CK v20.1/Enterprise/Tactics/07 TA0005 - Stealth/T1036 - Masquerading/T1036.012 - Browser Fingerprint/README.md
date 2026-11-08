# T1036.012 - Browser Fingerprint

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

Adversaries may attempt to blend in with legitimate traffic by spoofing browser and system attributes like operating system, system language, platform, user-agent string, resolution, time zone, etc.  The HTTP User-Agent request header is a string that lets servers and network peers identify the application, operating system, vendor, and/or version of the requesting user agent.(Citation: Mozilla User Agent)

Adversaries may gather this information through [System Information Discovery](https://attack.mitre.org/techniques/T1082) or by users navigating to adversary-controlled websites, and then use that information to craft their web traffic to evade defenses.(Citation: Gummy Browsers Targeted Browser Spoofing against State-of-the-Art Fingerprinting Techniques)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/012)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0512 - FatDuke](../../../../Threat%20Intelligence/Software/Malware/S0512%20-%20FatDuke.md) — [FatDuke](https://attack.mitre.org/software/S0512) has attempted to mimic a compromised user's traffic by using the same user agent as the installed browser.(Citation: ESET Dukes October 2019) [ESET Dukes October 2019](https://www.welivesecurity.com/wp-content/uploads/2019/10/ESET_Operation_Ghost_Dukes.pdf)
- [S9061 - LIGHTRAIL](../../../../Threat%20Intelligence/Software/Malware/S9061%20-%20LIGHTRAIL.md) — [LIGHTRAIL](https://attack.mitre.org/software/S9061) has leveraged hard-coded User Agent strings to mimic legitimate browser traffic. (Citation: Mandiant_UNC1549TTPsTools_Nov2025)(Citation: Mandiant_UNC1549_Feb2024) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense) · [Mandiant_UNC1549_Feb2024](https://cloud.google.com/blog/topics/threat-intelligence/suspected-iranian-unc1549-targets-israel-middle-east)
- [S9052 - MiniFast](../../../../Threat%20Intelligence/Software/Malware/S9052%20-%20MiniFast.md) — [MiniFast](https://attack.mitre.org/software/S9052) has blended into network traffic by mimicking a Chrome browser using the following User-Agent string: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/146.0.0.0 Safari/537.36`.(Citation: CheckPoint_NimbusManticore_May2026) [CheckPoint_NimbusManticore_May2026](https://research.checkpoint.com/2026/fast-and-furious-nimbus-manticore-operations-during-the-iranian-conflict/)

## Detection strategies

- [DET0898 - Detection of Spoofed User-Agent](../../../../Defenses/Detection%20Strategies/DET0898%20-%20Detection%20of%20Spoofed%20User-Agent.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Review and limit the fingerprinting surface to only necessary information on each browser to make the browser less unique. For example, the available fonts may be limited to a standard font list. (Citation: W3C) [W3C](https://www.w3.org/TR/fingerprinting-guidance/)

## Sources

- [Mozilla User Agent](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/User-Agent)
- [Gummy Browsers Targeted Browser Spoofing against State-of-the-Art Fingerprinting Techniques](https://arxiv.org/pdf/2110.10129)
