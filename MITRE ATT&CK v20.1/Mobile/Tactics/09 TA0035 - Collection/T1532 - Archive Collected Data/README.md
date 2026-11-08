# T1532 - Archive Collected Data

[Mobile](../../../README.md) / [Collection](../README.md)

Adversaries may compress and/or encrypt data that is collected prior to exfiltration. Compressing data can help to obfuscate its contents and minimize use of network resources. Encryption can be used to hide information that is being exfiltrated from detection or make exfiltration less conspicuous upon inspection by a defender. 

 

Both compression and encryption are done prior to exfiltration, and can be performed using a utility, programming library, or custom algorithm.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1532)

**Tactics**  [Collection](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S0422 - Anubis](../../../Threat%20Intelligence/Software/Malware/S0422%20-%20Anubis.md) — [Anubis](https://attack.mitre.org/software/S0422) exfiltrates data encrypted (with RC4) by its ransomware module.(Citation: Cofense Anubis) [Cofense Anubis](https://web.archive.org/web/20231222134431/https://cofense.com/blog/infostealer-keylogger-ransomware-one-anubis-targets-250-android-applications/)
- [S0540 - Asacub](../../../Threat%20Intelligence/Software/Malware/S0540%20-%20Asacub.md) — [Asacub](https://attack.mitre.org/software/S0540) has encrypted C2 communications using Base64-encoded RC4.(Citation: Securelist Asacub) [Securelist Asacub](https://securelist.com/the-rise-of-mobile-banker-asacub/87591/)
- [S1079 - BOULDSPY](../../../Threat%20Intelligence/Software/Malware/S1079%20-%20BOULDSPY.md) — [BOULDSPY](https://attack.mitre.org/software/S1079) can encrypt its data before exfiltration.(Citation: lookout_bouldspy_0423) [lookout_bouldspy_0423](https://www.lookout.com/blog/iranian-spyware-bouldspy)
- [S1094 - BRATA](../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) has compressed data with the `zlib` library before exfiltration.(Citation: cleafy_brata_0122) [cleafy_brata_0122](https://www.cleafy.com/cleafy-labs/how-brata-is-monitoring-your-bank-account)
- [C0033 - C0033](../../../Threat%20Intelligence/Campaigns/C0033%20-%20C0033.md) — During [C0033](https://attack.mitre.org/campaigns/C0033), [PROMETHIUM](https://attack.mitre.org/groups/G0056) used [StrongPity](https://attack.mitre.org/software/S0491) to exfiltrate encrypted data to the C2 server.(Citation: welivesec_strongpity) [welivesec_strongpity](https://www.welivesecurity.com/2023/01/10/strongpity-espionage-campaign-targeting-android-users/)
- [S1243 - DCHSpy](../../../Threat%20Intelligence/Software/Malware/S1243%20-%20DCHSpy.md) — [DCHSpy](https://attack.mitre.org/software/S1243) has compressed and encrypted collected data with a password from the C2 server.(Citation: Lookout_DCHSpy_July2025) [Lookout_DCHSpy_July2025](https://www.lookout.com/threat-intelligence/article/lookout-discovers-iranian-dchsy-surveillanceware)
- [S0505 - Desert Scorpion](../../../Threat%20Intelligence/Software/Malware/S0505%20-%20Desert%20Scorpion.md) — [Desert Scorpion](https://attack.mitre.org/software/S0505) can encrypt exfiltrated data.(Citation: Lookout Desert Scorpion) [Lookout Desert Scorpion](https://blog.lookout.com/desert-scorpion-google-play)
- [S0405 - Exodus](../../../Threat%20Intelligence/Software/Malware/S0405%20-%20Exodus.md) — [Exodus](https://attack.mitre.org/software/S0405) One encrypts data using XOR prior to exfiltration.(Citation: SWB Exodus March 2019) [SWB Exodus March 2019](https://web.archive.org/web/20200314194610/https://securitywithoutborders.org/blog/2019/03/29/exodus.html)
- [S0577 - FrozenCell](../../../Threat%20Intelligence/Software/Malware/S0577%20-%20FrozenCell.md) — [FrozenCell](https://attack.mitre.org/software/S0577) has compressed and encrypted data before exfiltration using password protected .7z archives.(Citation: Lookout FrozenCell) [Lookout FrozenCell](https://blog.lookout.com/frozencell-mobile-threat)
- [S0535 - Golden Cup](../../../Threat%20Intelligence/Software/Malware/S0535%20-%20Golden%20Cup.md) — [Golden Cup](https://attack.mitre.org/software/S0535) has encrypted exfiltrated data using AES in ECB mode.(Citation: Symantec GoldenCup) [Symantec GoldenCup](https://symantec-enterprise-blogs.security.com/blogs/expert-perspectives/goldencup-new-cyber-threat-targeting-world-cup-fans)
- [S0421 - GolfSpy](../../../Threat%20Intelligence/Software/Malware/S0421%20-%20GolfSpy.md) — [GolfSpy](https://attack.mitre.org/software/S0421) encrypts data using a simple XOR operation with a pre-configured key prior to exfiltration.(Citation: Trend Micro Bouncing Golf 2019) [Trend Micro Bouncing Golf 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/mobile-cyberespionage-campaign-bouncing-golf-affects-middle-east/)
- [S9048 - KoSpy](../../../Threat%20Intelligence/Software/Malware/S9048%20-%20KoSpy.md) — [KoSpy](https://attack.mitre.org/software/S9048) has encrypted collected data with a hardcoded AES key.(Citation: Lookout_KoSpy_March2025) [Lookout_KoSpy_March2025](https://security.lookout.com/threat-intelligence/article/lookout-discovers-new-spyware-by-north-korean-apt37)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) collects and compresses data to be exfiltrated using SSZipArchive.(Citation: LinkedIn Dmitry LightSpy 2025)(Citation: Threatfabric LightSpy 2024) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [S1082 - Sunbird](../../../Threat%20Intelligence/Software/Malware/S1082%20-%20Sunbird.md) — [Sunbird](https://attack.mitre.org/software/S1082) can exfiltrate collected data as a ZIP file.(Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)
- [S0424 - Triada](../../../Threat%20Intelligence/Software/Malware/S0424%20-%20Triada.md) — [Triada](https://attack.mitre.org/software/S0424) encrypts data prior to exfiltration.(Citation: Google Triada June 2019) [Google Triada June 2019](https://security.googleblog.com/2019/06/pha-family-highlights-triada.html)

## Detection strategies

- [DET0670 - Detection of Archive Collected Data](../../../Defenses/Detection%20Strategies/DET0670%20-%20Detection%20of%20Archive%20Collected%20Data.md)
