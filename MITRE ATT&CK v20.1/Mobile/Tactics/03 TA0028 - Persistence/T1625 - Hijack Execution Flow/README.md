# T1625 - Hijack Execution Flow

[Mobile](../../../README.md) / [Persistence](../README.md)

Adversaries may execute their own malicious payloads by hijacking the way operating systems run applications. Hijacking execution flow can be for the purposes of persistence since this hijacked execution may reoccur over time. 

There are many ways an adversary may hijack the flow of execution. A primary way is by manipulating how the operating system locates programs to be executed. How the operating system locates libraries to be used by a program can also be intercepted. Locations where the operating system looks for programs or resources, such as file directories, could also be poisoned to include malicious payloads.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1625)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Sub-techniques

- [T1625.001 - System Runtime API Hijacking](T1625.001%20-%20System%20Runtime%20API%20Hijacking/README.md)

## Mitigations

- [M1002 - Attestation](../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation could detect unauthorized operating system modifications.
- [M1004 - System Partition Integrity](../../../Defenses/Mitigations/M1004%20-%20System%20Partition%20Integrity.md) — Android Verified Boot can detect unauthorized modifications made to the system partition, which could lead to execution flow hijacking.(Citation: Android-VerifiedBoot) [Android-VerifiedBoot](https://source.android.com/security/verifiedboot/)

## Detection strategies

- [DET0694 - Detection of Hijack Execution Flow](../../../Defenses/Detection%20Strategies/DET0694%20-%20Detection%20of%20Hijack%20Execution%20Flow.md)

## Procedure examples

- [S0311 - YiSpecter](../../../Threat%20Intelligence/Software/Malware/S0311%20-%20YiSpecter.md) — [YiSpecter](https://attack.mitre.org/software/S0311) has hijacked normal application’s launch routines to display ads.(Citation: paloalto_yispecter_1015) [paloalto_yispecter_1015](https://unit42.paloaltonetworks.com/yispecter-first-ios-malware-attacks-non-jailbroken-ios-devices-by-abusing-private-apis/)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-27.html)
