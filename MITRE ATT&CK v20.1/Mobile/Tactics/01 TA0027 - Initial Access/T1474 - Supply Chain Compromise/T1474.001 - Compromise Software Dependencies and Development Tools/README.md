# T1474.001 - Compromise Software Dependencies and Development Tools

[Mobile](../../../../README.md) / [Initial Access](../../README.md) / [T1474 - Supply Chain Compromise](../README.md)

Adversaries may manipulate products or product delivery mechanisms prior to receipt by a final consumer for the purpose of data or system compromise. Applications often depend on external software to function properly. Popular open source projects that are used as dependencies in many applications may be targeted as a means to add malicious code to users of the dependency.(Citation: Grace-Advertisement)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1474/001)

**Tactics**  [Initial Access](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S0297 - XcodeGhost](../../../../Threat%20Intelligence/Software/Malware/S0297%20-%20XcodeGhost.md) — [XcodeGhost](https://attack.mitre.org/software/S0297) was injected into apps by a modified version of Xcode (Apple's software development tool).(Citation: PaloAlto-XcodeGhost1)(Citation: PaloAlto-XcodeGhost) [PaloAlto-XcodeGhost1](http://researchcenter.paloaltonetworks.com/2015/09/novel-malware-xcodeghost-modifies-xcode-infects-apple-ios-apps-and-hits-app-store/) · [PaloAlto-XcodeGhost](http://researchcenter.paloaltonetworks.com/2015/09/update-xcodeghost-attacker-can-phish-passwords-and-open-urls-though-infected-apps/)

## Mitigations

- [M1013 - Application Developer Guidance](../../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Application developers should be cautious when selecting third-party libraries to integrate into their application.

## Detection strategies

- [DET0704 - Detection of Compromise Software Dependencies and Development Tools](../../../../Defenses/Detection%20Strategies/DET0704%20-%20Detection%20of%20Compromise%20Software%20Dependencies%20and%20Development%20Tools.md)

## Sources

- [Grace-Advertisement](https://dl.acm.org/doi/10.1145/2185448.2185464)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-6.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-0.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-3.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-9.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-10.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-15.html)
