# T1629.003 - Disable or Modify Tools

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1629 - Impair Defenses](../README.md)

Adversaries may disable security tools to avoid potential detection of their tools and activities. This can take the form of disabling security software, modifying SELinux configuration, or other methods to interfere with security tools scanning or reporting information. This is typically done by abusing device administrator permissions or using system exploits to gain root access to the device to modify protected system files.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1629/003)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Mitigations

- [M1010 - Deploy Compromised Device Detection Method](../../../../Defenses/Mitigations/M1010%20-%20Deploy%20Compromised%20Device%20Detection%20Method.md) — Mobile security software can typically detect if a device has been rooted or jailbroken and can inform the user, who can then take appropriate action.
- [M1001 - Security Updates](../../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates frequently contain patches to vulnerabilities that can be exploited for root access.
- [M1004 - System Partition Integrity](../../../../Defenses/Mitigations/M1004%20-%20System%20Partition%20Integrity.md) — System partition integrity mechanisms, such as Verified Boot, can detect the unauthorized modification of system files.
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be taught the dangers of rooting or jailbreaking their device.

## Procedure examples

- [S1061 - AbstractEmu](../../../../Threat%20Intelligence/Software/Malware/S1061%20-%20AbstractEmu.md) — [AbstractEmu](https://attack.mitre.org/software/S1061) can disable Play Protect.(Citation: lookout_abstractemu_1021) [lookout_abstractemu_1021](https://www.lookout.com/blog/lookout-discovers-global-rooting-malware-campaign)
- [S1214 - Android/SpyAgent](../../../../Threat%20Intelligence/Software/Malware/S1214%20-%20Android%20-%20SpyAgent.md) — [Android/SpyAgent](https://attack.mitre.org/software/S1214) has attempted to detect anti-spam call applications.(Citation: McAfee MoqHao 2019) [McAfee MoqHao 2019](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/moqhao-related-android-spyware-targeting-japan-and-korea-found-on-google-play/)
- [S0422 - Anubis](../../../../Threat%20Intelligence/Software/Malware/S0422%20-%20Anubis.md) — [Anubis](https://attack.mitre.org/software/S0422) can modify administrator settings and disable Play Protect.(Citation: Cofense Anubis) [Cofense Anubis](https://web.archive.org/web/20231222134431/https://cofense.com/blog/infostealer-keylogger-ransomware-one-anubis-targets-250-android-applications/)
- [S1094 - BRATA](../../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can remove installed antivirus applications as well as disable Google Play Protect.(Citation: cleafy_brata_0122)(Citation: mcafee_brata_0421) [cleafy_brata_0122](https://www.cleafy.com/cleafy-labs/how-brata-is-monitoring-your-bank-account) · [mcafee_brata_0421](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/brata-keeps-sneaking-into-google-play-now-targeting-usa-and-spain/)
- [C0033 - C0033](../../../../Threat%20Intelligence/Campaigns/C0033%20-%20C0033.md) — During [C0033](https://attack.mitre.org/campaigns/C0033), [PROMETHIUM](https://attack.mitre.org/groups/G0056) used [StrongPity](https://attack.mitre.org/software/S0491) to modify permissions on a rooted device and tried to disable the SecurityLogAgent application.(Citation: welivesec_strongpity) [welivesec_strongpity](https://www.welivesecurity.com/2023/01/10/strongpity-espionage-campaign-targeting-android-users/)
- [S0480 - Cerberus](../../../../Threat%20Intelligence/Software/Malware/S0480%20-%20Cerberus.md) — [Cerberus](https://attack.mitre.org/software/S0480) disables Google Play Protect to prevent its discovery and deletion in the future.(Citation: Threat Fabric Cerberus) [Threat Fabric Cerberus](https://www.threatfabric.com/blogs/cerberus-a-new-banking-trojan-from-the-underworld.html)
- [S1083 - Chameleon](../../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has the ability to disable Google Play Protect.(Citation: cyble_chameleon_0423)(Citation: ThreatFabric_Chameleon_Dec2023) [cyble_chameleon_0423](https://cyble.com/blog/chameleon-a-new-android-malware-spotted-in-the-wild/) · [ThreatFabric_Chameleon_Dec2023](https://www.threatfabric.com/blogs/android-banking-trojan-chameleon-is-back-in-action)
- [S1054 - Drinik](../../../../Threat%20Intelligence/Software/Malware/S1054%20-%20Drinik.md) — [Drinik](https://attack.mitre.org/software/S1054) can use Accessibility Services to disable Google Play Protect.(Citation: cyble_drinik_1022) [cyble_drinik_1022](https://web.archive.org/web/20221114031945/https://blog.cyble.com/2022/10/27/drinik-malware-returns-with-advanced-capabilities-targeting-indian-taxpayers/)
- [S0420 - Dvmap](../../../../Threat%20Intelligence/Software/Malware/S0420%20-%20Dvmap.md) — [Dvmap](https://attack.mitre.org/software/S0420) can turn off `VerifyApps`, and can grant Device Administrator permissions via commands only, rather than using the UI.(Citation: SecureList DVMap June 2017) [SecureList DVMap June 2017](https://securelist.com/dvmap-the-first-android-malware-with-code-injection/78648/)
- [S1067 - FluBot](../../../../Threat%20Intelligence/Software/Malware/S1067%20-%20FluBot.md) — [FluBot](https://attack.mitre.org/software/S1067) can disable Google Play Protect to prevent detection.(Citation: proofpoint_flubot_0421)(Citation: Europol FluBot Jun2022) [proofpoint_flubot_0421](https://www.proofpoint.com/us/blog/threat-insight/flubot-android-malware-spreading-rapidly-through-europe-may-hit-us-soon) · [Europol FluBot Jun2022](https://www.europol.europa.eu/media-press/newsroom/news/takedown-of-sms-based-flubot-spyware-infecting-android-phones)
- [S0485 - Mandrake](../../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) can disable Play Protect.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S1195 - SpyC23](../../../../Threat%20Intelligence/Software/Malware/S1195%20-%20SpyC23.md) — [SpyC23](https://attack.mitre.org/software/S1195) has disabled play protect.(Citation: welivesecurity_apt-c-23) [welivesecurity_apt-c-23](https://web.archive.org/web/20201123042131/www.welivesecurity.com/2020/09/30/aptc23-group-evolves-its-android-spyware/)
- [S0494 - Zen](../../../../Threat%20Intelligence/Software/Malware/S0494%20-%20Zen.md) — [Zen](https://attack.mitre.org/software/S0494) can modify the SELinux enforcement mode.(Citation: Google Security Zen) [Google Security Zen](https://security.googleblog.com/2019/01/pha-family-highlights-zen-and-its.html)

## Detection strategies

- [DET0693 - Detection of Disable or Modify Tools](../../../../Defenses/Detection%20Strategies/DET0693%20-%20Detection%20of%20Disable%20or%20Modify%20Tools.md)
