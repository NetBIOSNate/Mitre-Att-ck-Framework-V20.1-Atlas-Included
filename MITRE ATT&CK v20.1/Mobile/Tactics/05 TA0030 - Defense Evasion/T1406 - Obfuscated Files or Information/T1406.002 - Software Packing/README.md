# T1406.002 - Software Packing

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1406 - Obfuscated Files or Information](../README.md)

Adversaries may perform software packing to conceal their code. Software packing is a method of compressing or encrypting an executable. Packing an executable changes the file signature in an attempt to avoid signature-based detection. Most decompression techniques decompress the executable code in memory. 

Utilities used to perform software packing are called packers. An example packer is FTT. A more comprehensive list of known packers is available, but adversaries may create their own packing techniques that do not leave the same artifacts as well-known packers to evade defenses.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1406/002)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S1094 - BRATA](../../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) has utilized commercial software packers.(Citation: mcafee_brata_0421) [mcafee_brata_0421](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/brata-keeps-sneaking-into-google-play-now-targeting-usa-and-spain/)
- [S0432 - Bread](../../../../Threat%20Intelligence/Software/Malware/S0432%20-%20Bread.md) — [Bread](https://attack.mitre.org/software/S0432) payloads have used several commercially available packers.(Citation: Google Bread) [Google Bread](https://security.googleblog.com/2020/01/pha-family-highlights-bread-and-friends.html)
- [S1225 - CherryBlos](../../../../Threat%20Intelligence/Software/Malware/S1225%20-%20CherryBlos.md) — [CherryBlos](https://attack.mitre.org/software/S1225) has used a commercial packer named Jiagubao to evade static detection.(Citation: TrendMicro_CherryBlos_July2023) [TrendMicro_CherryBlos_July2023](https://www.trendmicro.com/en_us/research/23/g/cherryblos-and-faketrade-android-malware-involved-in-scam-campai.html)
- [S9004 - Crocodilus](../../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) dropper and payload have been packed to hinder detection.(Citation: ThreatFabric_Crocodilus_June2025) [ThreatFabric_Crocodilus_June2025](https://www.threatfabric.com/blogs/crocodilus-mobile-malware-evolving-fast-going-global)
- [S0406 - Gustuff](../../../../Threat%20Intelligence/Software/Malware/S0406%20-%20Gustuff.md) — [Gustuff](https://attack.mitre.org/software/S0406) code is both obfuscated and packed with an FTT packer.(Citation: Talos Gustuff Apr 2019) [Talos Gustuff Apr 2019](https://blog.talosintelligence.com/2019/04/gustuff-targets-australia.html)
- [S1062 - S.O.V.A.](../../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) has been distributed in obfuscated and packed form.(Citation: threatfabric_sova_0921) [threatfabric_sova_0921](https://www.threatfabric.com/blogs/sova-new-trojan-with-fowl-intentions.html)

## Detection strategies

- [DET0644 - Detection of Software Packing](../../../../Defenses/Detection%20Strategies/DET0644%20-%20Detection%20of%20Software%20Packing.md)
