# T1644 - Out of Band Data

[Mobile](../../../README.md) / [Command and Control](../README.md)

Adversaries may communicate with compromised devices using out of band data streams. This could be done for a variety of reasons, including evading network traffic monitoring, as a backup method of command and control, or for data exfiltration if the device is not connected to any Internet-providing networks (i.e. cellular or Wi-Fi). Several out of band data streams exist, such as SMS messages, NFC, and Bluetooth. 

 

On Android, applications can read push notifications to capture content from SMS messages, or other out of band data streams. This requires that the user manually grant notification access to the application via the settings menu. However, the application could launch an Intent to take the user directly there. 

 

On iOS, there is no way to programmatically read push notifications.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1644)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S0304 - Android/Chuli.A](../../../Threat%20Intelligence/Software/Malware/S0304%20-%20Android%20-%20Chuli.A.md) — [Android/Chuli.A](https://attack.mitre.org/software/S0304) used SMS to receive command and control messages.(Citation: Kaspersky-WUC) [Kaspersky-WUC](https://securelist.com/android-trojan-found-in-targeted-attack-58/35552/)
- [S1079 - BOULDSPY](../../../Threat%20Intelligence/Software/Malware/S1079%20-%20BOULDSPY.md) — [BOULDSPY](https://attack.mitre.org/software/S1079) can use SMS to send C2 commands.(Citation: lookout_bouldspy_0423) [lookout_bouldspy_0423](https://www.lookout.com/blog/iranian-spyware-bouldspy)
- [S0655 - BusyGasper](../../../Threat%20Intelligence/Software/Malware/S0655%20-%20BusyGasper.md) — [BusyGasper](https://attack.mitre.org/software/S0655) can perform actions when one of two hardcoded magic SMS strings is received.(Citation: SecureList BusyGasper) [SecureList BusyGasper](https://securelist.com/busygasper-the-unfriendly-spy/87627/)
- [S0529 - CarbonSteal](../../../Threat%20Intelligence/Software/Malware/S0529%20-%20CarbonSteal.md) — [CarbonSteal](https://attack.mitre.org/software/S0529) has used specially crafted SMS messages to control the target device.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S0505 - Desert Scorpion](../../../Threat%20Intelligence/Software/Malware/S0505%20-%20Desert%20Scorpion.md) — [Desert Scorpion](https://attack.mitre.org/software/S0505) can be controlled using SMS messages.(Citation: Lookout Desert Scorpion) [Lookout Desert Scorpion](https://blog.lookout.com/desert-scorpion-google-play)
- [S0406 - Gustuff](../../../Threat%20Intelligence/Software/Malware/S0406%20-%20Gustuff.md) — [Gustuff](https://attack.mitre.org/software/S0406) can use SMS for command and control from a defined admin phone number.(Citation: Talos Gustuff Apr 2019) [Talos Gustuff Apr 2019](https://blog.talosintelligence.com/2019/04/gustuff-targets-australia.html)
- [S0407 - Monokle](../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can be controlled via email and SMS from a set of "control phones."(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)
- [S9040 - NGate](../../../Threat%20Intelligence/Software/Malware/S9040%20-%20NGate.md) — [NGate](https://attack.mitre.org/software/S9040) has used NFC to send the victim's card information through a server to an adversary-controlled device.(Citation: ESETStefankoOsmani_NGate_Aug2024)(Citation: CERTPL_NGate_Nov2025)(Citation: ESETStefanko_NGateVariant_Apr2026) [CERTPL_NGate_Nov2025](https://cert.pl/en/posts/2025/11/analiza-ngate/) · [ESETStefanko_NGateVariant_Apr2026](https://www.welivesecurity.com/en/eset-research/new-ngate-variant-hides-in-a-trojanized-nfc-payment-app/) · [ESETStefankoOsmani_NGate_Aug2024](https://www.welivesecurity.com/en/eset-research/ngate-android-malware-relays-nfc-traffic-to-steal-cash/)
- [S0316 - Pegasus for Android](../../../Threat%20Intelligence/Software/Malware/S0316%20-%20Pegasus%20for%20Android.md) — [Pegasus for Android](https://attack.mitre.org/software/S0316) uses SMS for command and control.(Citation: Lookout-PegasusAndroid) [Lookout-PegasusAndroid](https://blog.lookout.com/blog/2017/04/03/pegasus-android/)
- [S0289 - Pegasus for iOS](../../../Threat%20Intelligence/Software/Malware/S0289%20-%20Pegasus%20for%20iOS.md) — [Pegasus for iOS](https://attack.mitre.org/software/S0289) uses SMS for command and control.(Citation: Lookout-Pegasus) [Lookout-Pegasus](https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf)
- [S0295 - RCSAndroid](../../../Threat%20Intelligence/Software/Malware/S0295%20-%20RCSAndroid.md) — [RCSAndroid](https://attack.mitre.org/software/S0295) can use SMS for command and control.(Citation: TrendMicro-RCSAndroid) [TrendMicro-RCSAndroid](http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/)
- [S0411 - Rotexy](../../../Threat%20Intelligence/Software/Malware/S0411%20-%20Rotexy.md) — [Rotexy](https://attack.mitre.org/software/S0411) can be controlled through SMS messages.(Citation: securelist rotexy 2018) [securelist rotexy 2018](https://securelist.com/the-rotexy-mobile-trojan-banker-and-ransomware/88893/)
- [S1055 - SharkBot](../../../Threat%20Intelligence/Software/Malware/S1055%20-%20SharkBot.md) — [SharkBot](https://attack.mitre.org/software/S1055) can use the “Direct Reply” feature of Android to automatically reply to notifications with a message provided by C2.(Citation: nccgroup_sharkbot_0322) [nccgroup_sharkbot_0322](https://research.nccgroup.com/2022/03/03/sharkbot-a-new-generation-android-banking-trojan-being-distributed-on-google-play-store/)
- [S0327 - Skygofree](../../../Threat%20Intelligence/Software/Malware/S0327%20-%20Skygofree.md) — [Skygofree](https://attack.mitre.org/software/S0327) can be controlled via binary SMS.(Citation: Kaspersky-Skygofree) [Kaspersky-Skygofree](https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/)
- [S1195 - SpyC23](../../../Threat%20Intelligence/Software/Malware/S1195%20-%20SpyC23.md) — [SpyC23](https://attack.mitre.org/software/S1195) can receive Command and Control commands from SMS messages.(Citation: welivesecurity_apt-c-23) [welivesecurity_apt-c-23](https://web.archive.org/web/20201123042131/www.welivesecurity.com/2020/09/30/aptc23-group-evolves-its-android-spyware/)
- [S0324 - SpyDealer](../../../Threat%20Intelligence/Software/Malware/S0324%20-%20SpyDealer.md) — [SpyDealer](https://attack.mitre.org/software/S0324) enables remote control of the victim through SMS channels.(Citation: PaloAlto-SpyDealer) [PaloAlto-SpyDealer](https://researchcenter.paloaltonetworks.com/2017/07/unit42-spydealer-android-trojan-spying-40-apps/)
- [S0328 - Stealth Mango](../../../Threat%20Intelligence/Software/Malware/S0328%20-%20Stealth%20Mango.md) — [Stealth Mango](https://attack.mitre.org/software/S0328) uses commands received from text messages for C2.(Citation: Lookout-StealthMango) [Lookout-StealthMango](https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf)
- [S1216 - TriangleDB](../../../Threat%20Intelligence/Software/Malware/S1216%20-%20TriangleDB.md) — [TriangleDB](https://attack.mitre.org/software/S1216) has used the Protobuf library for command and control communication.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)
- [S0427 - TrickMo](../../../Threat%20Intelligence/Software/Malware/S0427%20-%20TrickMo.md) — [TrickMo](https://attack.mitre.org/software/S0427) can be controlled via encrypted SMS message.(Citation: SecurityIntelligence TrickMo) [SecurityIntelligence TrickMo](https://securityintelligence.com/posts/trickbot-pushing-a-2fa-bypass-app-to-bank-customers-in-germany/)

## Detection strategies

- [DET0688 - Detection of Out of Band Data](../../../Defenses/Detection%20Strategies/DET0688%20-%20Detection%20of%20Out%20of%20Band%20Data.md)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be instructed to not grant applications unexpected or unnecessary permissions.
