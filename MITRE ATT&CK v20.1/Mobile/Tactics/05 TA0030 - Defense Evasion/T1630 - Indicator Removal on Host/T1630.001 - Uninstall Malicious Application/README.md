# T1630.001 - Uninstall Malicious Application

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1630 - Indicator Removal on Host](../README.md)

Adversaries may include functionality in malware that uninstalls the malicious application from the device. This can be achieved by: 
 
* Abusing device owner permissions to perform silent uninstallation using device owner API calls. 
* Abusing root permissions to delete files from the filesystem. 
* Abusing the accessibility service. This requires sending an intent to the system to request uninstallation, and then abusing the accessibility service to click the proper places on the screen to confirm uninstallation.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1630/001)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Mitigations

- [M1002 - Attestation](../../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Attestation can detect rooted devices. Mobile security software can then use this information and take appropriate mitigation action. Attestation can detect rooted devices.
- [M1001 - Security Updates](../../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates typically provide patches for vulnerabilities that enable device rooting.
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Inform users that device rooting or granting unnecessary access to the accessibility service presents security risks that could be taken advantage of without their knowledge.

## Procedure examples

- [S1094 - BRATA](../../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can uninstall itself and remove traces of infection.(Citation: securelist_brata_0819)(Citation: mcafee_brata_0421) [mcafee_brata_0421](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/brata-keeps-sneaking-into-google-play-now-targeting-usa-and-spain/) · [securelist_brata_0819](https://securelist.com/spying-android-rat-from-brazil-brata/92775/)
- [S0480 - Cerberus](../../../../Threat%20Intelligence/Software/Malware/S0480%20-%20Cerberus.md) — [Cerberus](https://attack.mitre.org/software/S0480) can uninstall itself from a device on command.(Citation: Threat Fabric Cerberus) [Threat Fabric Cerberus](https://www.threatfabric.com/blogs/cerberus-a-new-banking-trojan-from-the-underworld.html)
- [S9004 - Crocodilus](../../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) has the ability to uninstall itself from the device.(Citation: ThreatFabric_Crocodilus_March2025) [ThreatFabric_Crocodilus_March2025](https://www.threatfabric.com/blogs/exposing-crocodilus-new-device-takeover-malware-targeting-android-devices)
- [S1092 - Escobar](../../../../Threat%20Intelligence/Software/Malware/S1092%20-%20Escobar.md) — [Escobar](https://attack.mitre.org/software/S1092) can uninstall itself and other applications.(Citation: Bleeipng Computer Escobar) [Bleeipng Computer Escobar](https://www.bleepingcomputer.com/news/security/android-malware-escobar-steals-your-google-authenticator-mfa-codes/)
- [S1062 - S.O.V.A.](../../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) can uninstall itself.(Citation: threatfabric_sova_0921) [threatfabric_sova_0921](https://www.threatfabric.com/blogs/sova-new-trojan-with-fowl-intentions.html)
- [S1055 - SharkBot](../../../../Threat%20Intelligence/Software/Malware/S1055%20-%20SharkBot.md) — [SharkBot](https://attack.mitre.org/software/S1055) has C2 commands that can uninstall the app from the infected device.(Citation: nccgroup_sharkbot_0322) [nccgroup_sharkbot_0322](https://research.nccgroup.com/2022/03/03/sharkbot-a-new-generation-android-banking-trojan-being-distributed-on-google-play-store/)
- [S0427 - TrickMo](../../../../Threat%20Intelligence/Software/Malware/S0427%20-%20TrickMo.md) — [TrickMo](https://attack.mitre.org/software/S0427) can uninstall itself from a device on command by abusing the accessibility service.(Citation: SecurityIntelligence TrickMo) [SecurityIntelligence TrickMo](https://securityintelligence.com/posts/trickbot-pushing-a-2fa-bypass-app-to-bank-customers-in-germany/)

## Detection strategies

- [DET0690 - Detection of Uninstall Malicious Application](../../../../Defenses/Detection%20Strategies/DET0690%20-%20Detection%20of%20Uninstall%20Malicious%20Application.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-43.html)
