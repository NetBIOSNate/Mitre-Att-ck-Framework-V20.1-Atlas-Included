# T1453 - Abuse Accessibility Features

[Mobile](../../../README.md) / [Collection](../README.md)

Adversaries may abuse accessibility features in Android devices to steal sensitive data and to spread malware to other devices. Accessibility features in Android are designed to assist users with disabilities, performing a variety of tasks, such as using Action Blocks to control lightbulbs, and changing the device’s user interface, such as changing the font size and adjusting contract or colors.(Citation: Google_AndroidAcsOverview) 

One example of how adversaries abuse accessibility features is overlaying an HTML object mimicking a legitimate login screen. The user types their credentials in the overlay HTML object, which is then sent to the adversaries.(Citation: SahinSRLabs_FluBot_Dec2021)  

Another example is a malicious accessibility feature acting as a keylogger. The keylogger monitors changes on the EditText fields and sends it to the adversaries.(Citation: SahinSRLabs_FluBot_Dec2021) This method of attack is also described in [Keylogging](https://attack.mitre.org/techniques/T1417/001); whereas [Abuse Accessibility Features](https://attack.mitre.org/techniques/T1453) captures the overall abuse of accessibility features.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1453)

**Tactics**  [Credential Access](../../06%20TA0031%20-%20Credential%20Access/README.md), [Collection](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S0422 - Anubis](../../../Threat%20Intelligence/Software/Malware/S0422%20-%20Anubis.md) — After accessibility service is granted, [Anubis](https://attack.mitre.org/software/S0422) lures the victim into changing the Accessibility settings on the device, disabling application removal, and executes screen taps and other commands without the victim’s knowledge.(Citation: Cyble_Anubis_May2021) [Cyble_Anubis_May2021](https://cyble.com/blog/mobile-malware-app-anubis-strikes-again-continues-to-lure-users-disguised-as-a-fake-antivirus/)
- [S1083 - Chameleon](../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — After accessibility permissions are granted, [Chameleon](https://attack.mitre.org/software/S1083) has used the Accessibility Service to perform a variety of actions, such as switching from biometric authentication to PIN authentication, automatically granting additional permissions, preventing uninstallation, disabling Play Protect.(Citation: cyble_chameleon_0423)(Citation: ThreatFabric_Chameleon_Dec2023) [cyble_chameleon_0423](https://cyble.com/blog/chameleon-a-new-android-malware-spotted-in-the-wild/) · [ThreatFabric_Chameleon_Dec2023](https://www.threatfabric.com/blogs/android-banking-trojan-chameleon-is-back-in-action)
- [S1225 - CherryBlos](../../../Threat%20Intelligence/Software/Malware/S1225%20-%20CherryBlos.md) — After accessibility permissions are granted, [CherryBlos](https://attack.mitre.org/software/S1225) has used the Accessibility Service to monitor when a wallet application launches and to steal credentials.(Citation: TrendMicro_CherryBlos_July2023) [TrendMicro_CherryBlos_July2023](https://www.trendmicro.com/en_us/research/23/g/cherryblos-and-faketrade-android-malware-involved-in-scam-campai.html)
- [S9004 - Crocodilus](../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) has requested for Accessibility Service to be enabled. Upon approval, [Crocodilus](https://attack.mitre.org/software/S9004) has connected to the C2 server to receive instructions, has continuously monitored Accessibility events, and has captured elements, such as wallet keys, displayed on the device screen.(Citation: ThreatFabric_Crocodilus_March2025) [ThreatFabric_Crocodilus_March2025](https://www.threatfabric.com/blogs/exposing-crocodilus-new-device-takeover-malware-targeting-android-devices)
- [S9005 - DocSwap](../../../Threat%20Intelligence/Software/Malware/S9005%20-%20DocSwap.md) — Once accessibility permissions are granted, [DocSwap](https://attack.mitre.org/software/S9005) has abused the Accessibility Service to execute a keylogging capability.(Citation: EnkiWhiteHat_KimsukyDOCSWAP_Dec2025)(Citation: S2W_DocSwap_Mar2025) [EnkiWhiteHat_KimsukyDOCSWAP_Dec2025](https://www.enki.co.kr/en/media-center/blog/kimsuky-distributing-malicious-mobile-app-via-qr-code) · [S2W_DocSwap_Mar2025](https://medium.com/s2wblog/detailed-analysis-of-docswap-malware-disguised-as-security-document-viewer-218a728c36ff)
- [S1067 - FluBot](../../../Threat%20Intelligence/Software/Malware/S1067%20-%20FluBot.md) — [FluBot](https://attack.mitre.org/software/S1067) abuses accessibility features in three ways: steal application credentials, evade detection and removal, and send SMS for lateral movement.(Citation: SahinSRLabs_FluBot_Dec2021) [SahinSRLabs_FluBot_Dec2021](https://www.srlabs.de/blog-post/flubot-abuses-accessibility-features-to-steal-data)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has abused the accessibility service to prevent the user from uninstalling [GodFather](https://attack.mitre.org/software/S1231), to exfiltrate Google Authenticator one-time passwords and to steal credentials.(Citation: MerkleScience_Godfather_April2023) [MerkleScience_Godfather_April2023](https://www.merklescience.com/blog/the-godfather-android-malware-threat-under-the-lens)
- [S9006 - VajraSpy](../../../Threat%20Intelligence/Software/Malware/S9006%20-%20VajraSpy.md) — [VajraSpy](https://attack.mitre.org/software/S9006) has exploited accessibility features to intercept and exfiltrate communication from WhatsApp, WhatsApp Business and Signal and to automatically enable necessary permissions on the user’s behalf.(Citation: ESET_VajraSpy_Feb2024) [ESET_VajraSpy_Feb2024](https://www.welivesecurity.com/en/eset-research/vajraspy-patchwork-espionage-apps/)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — First, users should be wary of clicking on suspicious text messages, links and emails. Secondly, users should be wary of granting applications accessibility features. Users may check applications that have been granted accessibility features by going to Settings, then Accessibility. Finally, users should be wary of downloading applications; although applications may be on the Google Play Store, they may not be benign (see [Application Versioning](https://attack.mitre.org/techniques/T1661)).

## Detection strategies

- [DET0697 - Detection of Abuse Accessibility Features](../../../Defenses/Detection%20Strategies/DET0697%20-%20Detection%20of%20Abuse%20Accessibility%20Features.md)

## Sources

- [Google_AndroidAcsOverview](https://support.google.com/accessibility/android/answer/6006564?hl=en&ref_topic=6007234&sjid=9936713164149272548-NA)
- [SahinSRLabs_FluBot_Dec2021](https://www.srlabs.de/blog-post/flubot-abuses-accessibility-features-to-steal-data)
