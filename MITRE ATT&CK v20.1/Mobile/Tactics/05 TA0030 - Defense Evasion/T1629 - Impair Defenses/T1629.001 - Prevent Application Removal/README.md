# T1629.001 - Prevent Application Removal

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1629 - Impair Defenses](../README.md)

Adversaries may abuse the Android device administration API to prevent the user from uninstalling a target application. In earlier versions of Android, device administrator applications needed their administration capabilities explicitly deactivated by the user before the application could be uninstalled. This was later updated so the user could deactivate and uninstall the administrator application in one step.

Adversaries may also abuse the device accessibility APIs to prevent removal. This set of APIs allows the application to perform certain actions on behalf of the user and programmatically determine what is being shown on the screen. The malicious application could monitor the device screen for certain modals (e.g., the confirmation modal to uninstall an application) and inject screen input or a back button tap to close the modal. For example, Android's `performGlobalAction(int)` API could be utilized to prevent the user from removing the malicious application from the device after installation. If the user wants to uninstall the malicious application, two cases may occur, both preventing the user from removing the application.

* Case 1: If the integer argument passed to the API call is `2` or `GLOBAL_ACTION_HOME`, the malicious application may direct the user to the home screen from settings screen 

* Case 2: If the integer argument passed to the API call is `1` or `GLOBAL_ACTION_BACK`, the malicious application may emulate the back press event

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1629/001)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Mitigations

- [M1012 - Enterprise Policy](../../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — An EMM/MDM can use the Android `DevicePolicyManager.setPermittedAccessibilityServices` method to set an explicit list of applications that are allowed to use Android's accessibility features.
- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Recent versions of Android modified how device administrator applications are uninstalled, making it easier for the user to remove them.
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be warned against granting access to accessibility features and device administration services, and to carefully scrutinize applications that request these dangerous permissions. Users should be taught how to boot into safe mode to uninstall malicious applications that may be interfering with the uninstallation process.

## Procedure examples

- [S0422 - Anubis](../../../../Threat%20Intelligence/Software/Malware/S0422%20-%20Anubis.md) — [Anubis](https://attack.mitre.org/software/S0422) may prevent malware's uninstallation by abusing Android’s ` performGlobalAction(int)` API call.
- [S1083 - Chameleon](../../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has prevented application removal by abusing Accessibility Services.(Citation: cyble_chameleon_0423)(Citation: ThreatFabric_Chameleon_Dec2023) [cyble_chameleon_0423](https://cyble.com/blog/chameleon-a-new-android-malware-spotted-in-the-wild/) · [ThreatFabric_Chameleon_Dec2023](https://www.threatfabric.com/blogs/android-banking-trojan-chameleon-is-back-in-action)
- [S9004 - Crocodilus](../../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) has the ability to prevent application removal.(Citation: ThreatFabric_Crocodilus_March2025) [ThreatFabric_Crocodilus_March2025](https://www.threatfabric.com/blogs/exposing-crocodilus-new-device-takeover-malware-targeting-android-devices)
- [S1067 - FluBot](../../../../Threat%20Intelligence/Software/Malware/S1067%20-%20FluBot.md) — [FluBot](https://attack.mitre.org/software/S1067) can use Accessibility Services to make removal of the malicious app difficult.(Citation: bitdefender_flubot_0524) [bitdefender_flubot_0524](https://www.bitdefender.com/blog/labs/new-flubot-campaign-sweeps-through-europe-targeting-android-and-ios-users-alike/)
- [S1231 - GodFather](../../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has abused the accessibility service to prevent the user from uninstalling itself.(Citation: MerkleScience_Godfather_April2023) [MerkleScience_Godfather_April2023](https://www.merklescience.com/blog/the-godfather-android-malware-threat-under-the-lens)
- [S0406 - Gustuff](../../../../Threat%20Intelligence/Software/Malware/S0406%20-%20Gustuff.md) — [Gustuff](https://attack.mitre.org/software/S0406) may prevent application removal by abusing Android’s ` performGlobalAction(int)` API call.
- [S0485 - Mandrake](../../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) can abuse device administrator permissions to ensure that it cannot be uninstalled until its permissions are revoked.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0286 - OBAD](../../../../Threat%20Intelligence/Software/Malware/S0286%20-%20OBAD.md) — [OBAD](https://attack.mitre.org/software/S0286) abuses device administrator access to make it more difficult for users to remove the application.(Citation: TrendMicro-Obad) [TrendMicro-Obad](http://blog.trendmicro.com/trendlabs-security-intelligence/cybercriminals-improve-android-malware-stealth-routines-with-obad/)
- [S1062 - S.O.V.A.](../../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) can resist removal by going to the home screen during uninstall.(Citation: threatfabric_sova_0921) [threatfabric_sova_0921](https://www.threatfabric.com/blogs/sova-new-trojan-with-fowl-intentions.html)

## Detection strategies

- [DET0598 - Detection of Prevent Application Removal](../../../../Defenses/Detection%20Strategies/DET0598%20-%20Detection%20of%20Prevent%20Application%20Removal.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-22.html)
