# T1632.001 - Code Signing Policy Modification

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1632 - Subvert Trust Controls](../README.md)

Adversaries may modify code signing policies to enable execution of applications signed with unofficial or unknown keys. Code signing provides a level of authenticity on an app from a developer, guaranteeing that the program has not been tampered with and comes from an official source. Security controls can include enforcement mechanisms to ensure that only valid, signed code can be run on a device. 

Mobile devices generally enable these security controls by default, such as preventing the installation of unknown applications on Android. Adversaries may modify these policies in a number of ways, including [Input Injection](https://attack.mitre.org/techniques/T1516) or malicious configuration profiles.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1632/001)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S0505 - Desert Scorpion](../../../../Threat%20Intelligence/Software/Malware/S0505%20-%20Desert%20Scorpion.md) — If running on a Huawei device, [Desert Scorpion](https://attack.mitre.org/software/S0505) adds itself to the protected apps list, which allows it to run with the screen off.(Citation: Lookout Desert Scorpion) [Lookout Desert Scorpion](https://blog.lookout.com/desert-scorpion-google-play)
- [S0420 - Dvmap](../../../../Threat%20Intelligence/Software/Malware/S0420%20-%20Dvmap.md) — [Dvmap](https://attack.mitre.org/software/S0420) can enable installation of apps from unknown sources.(Citation: SecureList DVMap June 2017) [SecureList DVMap June 2017](https://securelist.com/dvmap-the-first-android-malware-with-code-injection/78648/)
- [S0551 - GoldenEagle](../../../../Threat%20Intelligence/Software/Malware/S0551%20-%20GoldenEagle.md) — [GoldenEagle](https://attack.mitre.org/software/S0551) has modified or configured proxy information.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S0485 - Mandrake](../../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) can enable app installation from unknown sources.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0549 - SilkBean](../../../../Threat%20Intelligence/Software/Malware/S0549%20-%20SilkBean.md) — [SilkBean](https://attack.mitre.org/software/S0549) has attempted to trick users into enabling installation of applications from unknown sources.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S1056 - TianySpy](../../../../Threat%20Intelligence/Software/Malware/S1056%20-%20TianySpy.md) — [TianySpy](https://attack.mitre.org/software/S1056) can install malicious configurations on iPhones to allow malware to be installed via Ad Hoc distribution.(Citation: trendmicro_tianyspy_0122) [trendmicro_tianyspy_0122](https://www.trendmicro.com/en_us/research/22/a/tianyspy-malware-uses-smishing-disguised-as-message-from-telco.html)
- [G0112 - Windshift](../../../../Threat%20Intelligence/Groups/G0112%20-%20Windshift.md) — [Windshift](https://attack.mitre.org/groups/G0112) has installed malicious MDM profiles on iOS devices as part of Operation ROCK.(Citation: BlackBerry Bahamut) [BlackBerry Bahamut](https://www.blackberry.com/us/en/pdfviewer?file=/content/dam/blackberry-com/asset/enterprise/pdf/direct/report-spark-bahamut.pdf)
- [S0490 - XLoader for iOS](../../../../Threat%20Intelligence/Software/Malware/S0490%20-%20XLoader%20for%20iOS.md) — [XLoader for iOS](https://attack.mitre.org/software/S0490) has been installed via a malicious configuration profile.(Citation: TrendMicro-XLoader-FakeSpy) [TrendMicro-XLoader-FakeSpy](https://blog.trendmicro.com/trendlabs-security-intelligence/new-version-of-xloader-that-disguises-as-android-apps-and-an-ios-profile-holds-new-links-to-fakespy/)
- [S0311 - YiSpecter](../../../../Threat%20Intelligence/Software/Malware/S0311%20-%20YiSpecter.md) — [YiSpecter](https://attack.mitre.org/software/S0311) has used fake Verisign and Symantec certificates to bypass malware detection systems. [YiSpecter](https://attack.mitre.org/software/S0311) has also signed malicious apps with iOS enterprise certificates to work on non-jailbroken iOS devices.(Citation: paloalto_yispecter_1015) [paloalto_yispecter_1015](https://unit42.paloaltonetworks.com/yispecter-first-ios-malware-attacks-non-jailbroken-ios-devices-by-abusing-private-apis/)

## Mitigations

- [M1012 - Enterprise Policy](../../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — On iOS, the `allowEnterpriseAppTrust` and `allowEnterpriseAppTrustModification` configuration profile restrictions can be used to prevent users from installing apps signed using enterprise distribution keys.
- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Mobile OSes have implemented measures to make it more difficult to trick users into installing untrusted certificates and configurations. iOS 10.3 and higher add an additional step for users to install new trusted CA certificates and configuration profiles. On Android, apps that target compatibility with Android 7 and higher (API Level 24) default to only trusting CA certificates that are bundled with the operating system, not CA certificates that are added by the user or administrator, hence decreasing their susceptibility to successful adversary-in-the-middle attack.(Citation: Symantec-iOSProfile2)(Citation: Android-TrustedCA) [Symantec-iOSProfile2](https://www.symantec.com/connect/blogs/apple-ios-103-finally-battles-malicious-profiles) · [Android-TrustedCA](https://android-developers.googleblog.com/2016/07/changes-to-trusted-certificate.html)
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Typically, insecure or malicious configuration settings are not installed without the user's consent. Users should be advised not to install unexpected configuration settings (CA certificates, iOS Configuration Profiles, Mobile Device Management server provisioning).

## Detection strategies

- [DET0619 - Detection of Code Signing Policy Modification](../../../../Defenses/Detection%20Strategies/DET0619%20-%20Detection%20of%20Code%20Signing%20Policy%20Modification.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/stack-threats/STA-7.html)
