# T1661 - Application Versioning

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

An adversary may push an update to a previously benign application to add malicious code. This can be accomplished by pushing an initially benign, functional application to a trusted application store, such as the Google Play Store or the Apple App Store. This allows the adversary to establish a trusted userbase that may grant permissions to the application prior to the introduction of malicious code. Then, an application update could be pushed to introduce malicious code.(Citation: android_app_breaking_bad)

This technique could also be accomplished by compromising a developer’s account. This would allow an adversary to take advantage of an existing userbase without having to establish the userbase themselves.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1661)

**Tactics**  [Initial Access](../../01%20TA0027%20-%20Initial%20Access/README.md), [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Detection strategies

- [DET0652 - Detection of Application Versioning](../../../Defenses/Detection%20Strategies/DET0652%20-%20Detection%20of%20Application%20Versioning.md)

## Mitigations

- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — Enterprises can provision policies to mobile devices for application allow-listing, ensuring only approved applications are installed onto mobile devices.
- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 11 and above implement application hibernation, which can hibernate an application that has not been used for a few months and can reset the application’s permission requests.(Citation: app_hibernation) [app_hibernation](https://developer.android.com/topic/performance/app-hibernation)

## Procedure examples

- [S1055 - SharkBot](../../../Threat%20Intelligence/Software/Malware/S1055%20-%20SharkBot.md) — [SharkBot](https://attack.mitre.org/software/S1055) initially poses as a benign application, then malware is downloaded and executed after an application update.(Citation: nccgroup_sharkbot_0322) [nccgroup_sharkbot_0322](https://research.nccgroup.com/2022/03/03/sharkbot-a-new-generation-android-banking-trojan-being-distributed-on-google-play-store/)

## Sources

- [android_app_breaking_bad](https://www.welivesecurity.com/2023/05/23/android-app-breaking-bad-legitimate-screen-recording-file-exfiltration/)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-20.html)
