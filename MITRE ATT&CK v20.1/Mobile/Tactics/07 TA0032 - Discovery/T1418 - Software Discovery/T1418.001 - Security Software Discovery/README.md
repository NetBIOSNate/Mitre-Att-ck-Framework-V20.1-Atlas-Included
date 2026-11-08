# T1418.001 - Security Software Discovery

[Mobile](../../../../README.md) / [Discovery](../../README.md) / [T1418 - Software Discovery](../README.md)

Adversaries may attempt to get a listing of security applications and configurations that are installed on a device. This may include things such as mobile security products. Adversaries may use the information from [Security Software Discovery](https://attack.mitre.org/techniques/T1418/001) during automated discovery to shape follow-on behaviors, including whether or not to fully infect the target and/or attempt specific actions.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1418/001)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Detection strategies

- [DET0680 - Detection of Security Software Discovery](../../../../Defenses/Detection%20Strategies/DET0680%20-%20Detection%20of%20Security%20Software%20Discovery.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 11 introduced privacy enhancements to package visibility, filtering results that are returned from the package manager. iOS 12 removed the private API that could previously be used to list installed applications on non-app store applications.(Citation: Android Package Visibility) [Android Package Visibility](https://developer.android.com/training/package-visibility)
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — iOS users should be instructed to not download applications from unofficial sources, as applications distributed via the Apple App Store cannot list installed applications on a device.

## Procedure examples

- [S1094 - BRATA](../../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can search for specifically installed security applications.(Citation: cleafy_brata_0122) [cleafy_brata_0122](https://www.cleafy.com/cleafy-labs/how-brata-is-monitoring-your-bank-account)
- [S0522 - Exobot](../../../../Threat%20Intelligence/Software/Malware/S0522%20-%20Exobot.md) — [Exobot](https://attack.mitre.org/software/S0522) can obtain a list of installed applications and can detect if an antivirus application is running, and close it if it is.(Citation: Threat Fabric Exobot) [Threat Fabric Exobot](https://www.threatfabric.com/blogs/exobot_android_banking_trojan_on_the_rise.html)
- [S0406 - Gustuff](../../../../Threat%20Intelligence/Software/Malware/S0406%20-%20Gustuff.md) — [Gustuff](https://attack.mitre.org/software/S0406) checks for antivirus software contained in a predefined list.(Citation: Talos Gustuff Apr 2019) [Talos Gustuff Apr 2019](https://blog.talosintelligence.com/2019/04/gustuff-targets-australia.html)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-12.html)
