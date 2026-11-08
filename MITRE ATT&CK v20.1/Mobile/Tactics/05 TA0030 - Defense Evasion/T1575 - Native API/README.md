# T1575 - Native API

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may use Android’s Native Development Kit (NDK) to write native functions that can achieve execution of binaries or functions. Like system calls on a traditional desktop operating system, native code achieves execution on a lower level than normal Android SDK calls.

The NDK allows developers to write native code in C or C++ that is compiled directly to machine code, avoiding all intermediate languages and steps in compilation that higher level languages, like Java, typically have. The Java Native Interface (JNI) is the component that allows Java functions in the Android app to call functions in a native library.(Citation: Google NDK Getting Started)

Adversaries may also choose to use native functions to execute malicious code since native actions are typically much more difficult to analyze than standard, non-native behaviors.(Citation: MITRE App Vetting Effectiveness)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1575)

**Tactics**  [Execution](../../02%20TA0041%20-%20Execution/README.md), [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S0540 - Asacub](../../../Threat%20Intelligence/Software/Malware/S0540%20-%20Asacub.md) — [Asacub](https://attack.mitre.org/software/S0540) has implemented functions in native code.(Citation: Securelist Asacub) [Securelist Asacub](https://securelist.com/the-rise-of-mobile-banker-asacub/87591/)
- [S0432 - Bread](../../../Threat%20Intelligence/Software/Malware/S0432%20-%20Bread.md) — [Bread](https://attack.mitre.org/software/S0432) has used native code in an attempt to disguise malicious functionality.(Citation: Google Bread) [Google Bread](https://security.googleblog.com/2020/01/pha-family-highlights-bread-and-friends.html)
- [S0529 - CarbonSteal](../../../Threat%20Intelligence/Software/Malware/S0529%20-%20CarbonSteal.md) — [CarbonSteal](https://attack.mitre.org/software/S0529) has seen native libraries used in some reported samples (Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S1083 - Chameleon](../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has used the KeyguardManager API to evaluate the device’s locking mechanism and the AlarmManager API to schedule tasks.(Citation: ThreatFabric_Chameleon_Dec2023) [ThreatFabric_Chameleon_Dec2023](https://www.threatfabric.com/blogs/android-banking-trojan-chameleon-is-back-in-action)
- [S0555 - CHEMISTGAMES](../../../Threat%20Intelligence/Software/Malware/S0555%20-%20CHEMISTGAMES.md) — [CHEMISTGAMES](https://attack.mitre.org/software/S0555) has utilized native code to decrypt its malicious payload.(Citation: CYBERWARCON CHEMISTGAMES) [CYBERWARCON CHEMISTGAMES](https://www.youtube.com/watch?v=xoNSbm1aX_w)
- [S9005 - DocSwap](../../../Threat%20Intelligence/Software/Malware/S9005%20-%20DocSwap.md) — [DocSwap](https://attack.mitre.org/software/S9005) has decrypted the encrypted APK file security.dat using the `decryptFile` function in the `native-lib` library.(Citation: EnkiWhiteHat_KimsukyDOCSWAP_Dec2025) [EnkiWhiteHat_KimsukyDOCSWAP_Dec2025](https://www.enki.co.kr/en/media-center/blog/kimsuky-distributing-malicious-mobile-app-via-qr-code)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has hooked onto the `getEnabledAccessibilityServiceList` API to return an empty list of active services, which hides [GodFather](https://attack.mitre.org/software/S1231) and other active services.(Citation: ZimperiumOrtegaPratapagiri_GodFather_Jun2025) [ZimperiumOrtegaPratapagiri_GodFather_Jun2025](https://zimperium.com/blog/your-mobile-app-their-playground-the-dark-side-of-the-virtualization)
- [S0544 - HenBox](../../../Threat%20Intelligence/Software/Malware/S0544%20-%20HenBox.md) — [HenBox](https://attack.mitre.org/software/S0544) has contained native libraries.(Citation: Palo Alto HenBox) [Palo Alto HenBox](https://unit42.paloaltonetworks.com/unit42-henbox-chickens-come-home-roost/)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185)'s main executable and modules use native libraries to execute targeted functionality.(Citation: Threatfabric LightSpy 2023)(Citation: MelikovBlackBerry LightSpy 2024)(Citation: LinkedIn Dmitry LightSpy 2025)(Citation: Threatfabric LightSpy 2024) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [MelikovBlackBerry LightSpy 2024](https://blogs.blackberry.com/en/2024/04/lightspy-returns-renewed-espionage-campaign-targets-southern-asia-possibly-india) · [Threatfabric LightSpy 2023](https://www.threatfabric.com/blogs/lightspy-mapt-mobile-payment-system-attack) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [C0054 - Operation Triangulation](../../../Threat%20Intelligence/Campaigns/C0054%20-%20Operation%20Triangulation.md) — During [Operation Triangulation](https://attack.mitre.org/campaigns/C0054), the threat actors use the Audio Queue API to record audio.(Citation: SecureList OpTriangulation 23Oct2023)(Citation: SecureList OpTriangulation Dec2023) [SecureList OpTriangulation 23Oct2023](https://securelist.com/triangulation-validators-modules/110847/) · [SecureList OpTriangulation Dec2023](https://securelist.com/operation-triangulation-the-last-hardware-mystery/111669/)
- [S0545 - TERRACOTTA](../../../Threat%20Intelligence/Software/Malware/S0545%20-%20TERRACOTTA.md) — [TERRACOTTA](https://attack.mitre.org/software/S0545) has included native modules.(Citation: WhiteOps TERRACOTTA) [WhiteOps TERRACOTTA](https://www.whiteops.com/blog/terracotta-android-malware-a-technical-study)

## Detection strategies

- [DET0717 - Detection of Native API](../../../Defenses/Detection%20Strategies/DET0717%20-%20Detection%20of%20Native%20API.md)

## Sources

- [Google NDK Getting Started](https://developer.android.com/ndk/guides)
- [MITRE App Vetting Effectiveness](https://www.mitre.org/sites/default/files/publications/pr-16-4772-analyzing-effectiveness-mobile-app-vetting-tools-report.pdf)
