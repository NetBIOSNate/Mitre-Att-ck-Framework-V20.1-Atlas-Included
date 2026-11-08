# T1616 - Call Control

[Mobile](../../../README.md) / [Impact](../README.md)

Adversaries may make, forward, or block phone calls without user authorization. This could be used for adversary goals such as audio surveillance, blocking or forwarding calls from the device owner, or C2 communication.

Several permissions may be used to programmatically control phone calls, including:

* `ANSWER_PHONE_CALLS` - Allows the application to answer incoming phone calls(Citation: Android Permissions)
* `CALL_PHONE` - Allows the application to initiate a phone call without going through the Dialer interface(Citation: Android Permissions)
* `PROCESS_OUTGOING_CALLS` - Allows the application to see the number being dialed during an outgoing call with the option to redirect the call to a different number or abort the call altogether(Citation: Android Permissions)
* `MANAGE_OWN_CALLS` - Allows a calling application which manages its own calls through the self-managed `ConnectionService` APIs(Citation: Android Permissions)
* `BIND_TELECOM_CONNECTION_SERVICE` - Required permission when using a `ConnectionService`(Citation: Android Permissions)
* `WRITE_CALL_LOG` - Allows an application to write to the device call log, potentially to hide malicious phone calls(Citation: Android Permissions)

When granted some of these permissions, an application can make a phone call without opening the dialer first. However, if an application desires to simply redirect the user to the dialer with a phone number filled in, it can launch an Intent using `Intent.ACTION_DIAL`, which requires no specific permissions. This then requires the user to explicitly initiate the call or use some form of [Input Injection](https://attack.mitre.org/techniques/T1516) to programmatically initiate it.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1616)

**Tactics**  [Collection](../../09%20TA0035%20-%20Collection/README.md), [Command and Control](../../10%20TA0037%20-%20Command%20and%20Control/README.md), [Impact](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S1214 - Android/SpyAgent](../../../Threat%20Intelligence/Software/Malware/S1214%20-%20Android%20-%20SpyAgent.md) — [Android/SpyAgent](https://attack.mitre.org/software/S1214) can execute an automated phone call.(Citation: McAfee MoqHao 2019) [McAfee MoqHao 2019](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/moqhao-related-android-spyware-targeting-japan-and-korea-found-on-google-play/)
- [S0292 - AndroRAT](../../../Threat%20Intelligence/Software/Malware/S0292%20-%20AndroRAT.md) — [AndroRAT](https://attack.mitre.org/software/S0292) can make phone calls.(Citation: forcepoint_bitter) [forcepoint_bitter](https://web.archive.org/web/20220706125432/https://www.forcepoint.com/blog/x-labs/bitter-targeted-attack-against-pakistan)
- [S0422 - Anubis](../../../Threat%20Intelligence/Software/Malware/S0422%20-%20Anubis.md) — [Anubis](https://attack.mitre.org/software/S0422) can make phone calls.(Citation: Cofense Anubis) [Cofense Anubis](https://web.archive.org/web/20231222134431/https://cofense.com/blog/infostealer-keylogger-ransomware-one-anubis-targets-250-android-applications/)
- [S1094 - BRATA](../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can hide incoming calls by setting ring volume to 0 and showing a blank screen overlay.(Citation: mcafee_brata_0421) [mcafee_brata_0421](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/brata-keeps-sneaking-into-google-play-now-targeting-usa-and-spain/)
- [S0655 - BusyGasper](../../../Threat%20Intelligence/Software/Malware/S0655%20-%20BusyGasper.md) — [BusyGasper](https://attack.mitre.org/software/S0655) can open a hidden menu when a specific phone number is called from the infected device.(Citation: SecureList BusyGasper) [SecureList BusyGasper](https://securelist.com/busygasper-the-unfriendly-spy/87627/)
- [S0529 - CarbonSteal](../../../Threat%20Intelligence/Software/Malware/S0529%20-%20CarbonSteal.md) — [CarbonSteal](https://attack.mitre.org/software/S0529) can silently accept an incoming phone call.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S1083 - Chameleon](../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has the ability to control calls.(Citation: ThreatFabric_Chameleon_Dec2023) [ThreatFabric_Chameleon_Dec2023](https://www.threatfabric.com/blogs/android-banking-trojan-chameleon-is-back-in-action)
- [S9004 - Crocodilus](../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) has the ability to enable call forwarding.(Citation: ThreatFabric_Crocodilus_March2025) [ThreatFabric_Crocodilus_March2025](https://www.threatfabric.com/blogs/exposing-crocodilus-new-device-takeover-malware-targeting-android-devices)
- [S9005 - DocSwap](../../../Threat%20Intelligence/Software/Malware/S9005%20-%20DocSwap.md) — [DocSwap](https://attack.mitre.org/software/S9005) has requested for the `CALL_PHONE` permission to make phone calls.(Citation: EnkiWhiteHat_KimsukyDOCSWAP_Dec2025)(Citation: S2W_DocSwap_Mar2025) [EnkiWhiteHat_KimsukyDOCSWAP_Dec2025](https://www.enki.co.kr/en/media-center/blog/kimsuky-distributing-malicious-mobile-app-via-qr-code) · [S2W_DocSwap_Mar2025](https://medium.com/s2wblog/detailed-analysis-of-docswap-malware-disguised-as-security-document-viewer-218a728c36ff)
- [S1054 - Drinik](../../../Threat%20Intelligence/Software/Malware/S1054%20-%20Drinik.md) — [Drinik](https://attack.mitre.org/software/S1054) can use the Android `CallScreeningService` to silently block incoming calls.(Citation: cyble_drinik_1022) [cyble_drinik_1022](https://web.archive.org/web/20221114031945/https://blog.cyble.com/2022/10/27/drinik-malware-returns-with-advanced-capabilities-targeting-indian-taxpayers/)
- [S1092 - Escobar](../../../Threat%20Intelligence/Software/Malware/S1092%20-%20Escobar.md) — [Escobar](https://attack.mitre.org/software/S1092) can initiate phone calls.(Citation: Bleeipng Computer Escobar) [Bleeipng Computer Escobar](https://www.bleepingcomputer.com/news/security/android-malware-escobar-steals-your-google-authenticator-mfa-codes/)
- [S1080 - Fakecalls](../../../Threat%20Intelligence/Software/Malware/S1080%20-%20Fakecalls.md) — [Fakecalls](https://attack.mitre.org/software/S1080) can intercept and imitate phone conversations by breaking the connection and displaying a fake call screen. It can also make outgoing calls and spoof incoming calls.(Citation: kaspersky_fakecalls_0422) [kaspersky_fakecalls_0422](https://www.kaspersky.com/blog/fakecalls-banking-trojan/44072/)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has requested for the `CALL_PHONE` permission to initiate phone calls.(Citation: MerkleScience_Godfather_April2023) [MerkleScience_Godfather_April2023](https://www.merklescience.com/blog/the-godfather-android-malware-threat-under-the-lens)
- [S0407 - Monokle](../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can be controlled via phone call from a set of "control phones."(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)
- [S1195 - SpyC23](../../../Threat%20Intelligence/Software/Malware/S1195%20-%20SpyC23.md) — [SpyC23](https://attack.mitre.org/software/S1195) can make phone calls.(Citation: welivesecurity_apt-c-23)(Citation: SentinelLabs AridViper 2023) [SentinelLabs AridViper 2023](https://www.sentinelone.com/labs/arid-viper-apts-nest-of-spyc23-malware-continues-to-target-android-devices/) · [welivesecurity_apt-c-23](https://web.archive.org/web/20201123042131/www.welivesecurity.com/2020/09/30/aptc23-group-evolves-its-android-spyware/)
- [S1069 - TangleBot](../../../Threat%20Intelligence/Software/Malware/S1069%20-%20TangleBot.md) — [TangleBot](https://attack.mitre.org/software/S1069) can make and block phone calls.(Citation: cloudmark_tanglebot_0921) [cloudmark_tanglebot_0921](https://www.cloudmark.com/en/blog/malware/tanglebot-new-advanced-sms-malware-targets-mobile-users-across-us-and-canada-covid-19)
- [S9006 - VajraSpy](../../../Threat%20Intelligence/Software/Malware/S9006%20-%20VajraSpy.md) — [VajraSpy](https://attack.mitre.org/software/S9006) has requested for `android.permission.CALL_PHONE`.(Citation: K7Dhanalakshmi_VajraSpy_April2022) [K7Dhanalakshmi_VajraSpy_April2022](https://labs.k7computing.com/index.php/vajraspy-an-android-rat/)

## Detection strategies

- [DET0703 - Detection of Call Control](../../../Defenses/Detection%20Strategies/DET0703%20-%20Detection%20of%20Call%20Control.md)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be encouraged to be very careful with what applications they grant phone call-based permissions to. Further, users should not change their default call handler to applications they do not recognize.

## Sources

- [Android Permissions](https://developer.android.com/reference/android/Manifest.permission)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-41.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-42.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-36.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-18.html)
