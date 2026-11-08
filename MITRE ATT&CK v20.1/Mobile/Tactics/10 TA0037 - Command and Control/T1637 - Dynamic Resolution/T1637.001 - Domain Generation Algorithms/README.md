# T1637.001 - Domain Generation Algorithms

[Mobile](../../../../README.md) / [Command and Control](../../README.md) / [T1637 - Dynamic Resolution](../README.md)

Adversaries may use [Domain Generation Algorithms](https://attack.mitre.org/techniques/T1637/001) (DGAs) to procedurally generate domain names for uses such as command and control communication   or malicious application distribution.(Citation: securelist rotexy 2018)

DGAs increase the difficulty for defenders to block, track, or take over the command and control channel, as there could potentially be thousands of domains that malware can check for instructions.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1637/001)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S1067 - FluBot](../../../../Threat%20Intelligence/Software/Malware/S1067%20-%20FluBot.md) — [FluBot](https://attack.mitre.org/software/S1067) can use Domain Generation Algorithms to connect to the C2 server.(Citation: proofpoint_flubot_0421) [proofpoint_flubot_0421](https://www.proofpoint.com/us/blog/threat-insight/flubot-android-malware-spreading-rapidly-through-europe-may-hit-us-soon)
- [S0485 - Mandrake](../../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) has used domain generation algorithms.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0411 - Rotexy](../../../../Threat%20Intelligence/Software/Malware/S0411%20-%20Rotexy.md) — [Rotexy](https://attack.mitre.org/software/S0411) procedurally generates subdomains for command and control communication.(Citation: securelist rotexy 2018) [securelist rotexy 2018](https://securelist.com/the-rotexy-mobile-trojan-banker-and-ransomware/88893/)
- [S1055 - SharkBot](../../../../Threat%20Intelligence/Software/Malware/S1055%20-%20SharkBot.md) — [SharkBot](https://attack.mitre.org/software/S1055) contains domain generation algorithms to use as backups in case the hardcoded C2 domains are unavailable.(Citation: nccgroup_sharkbot_0322) [nccgroup_sharkbot_0322](https://research.nccgroup.com/2022/03/03/sharkbot-a-new-generation-android-banking-trojan-being-distributed-on-google-play-store/)

## Detection strategies

- [DET0669 - Detection of Domain Generation Algorithms](../../../../Defenses/Detection%20Strategies/DET0669%20-%20Detection%20of%20Domain%20Generation%20Algorithms.md)

## Sources

- [Data Driven Security DGA](https://datadrivensecurity.info/blog/posts/2014/Oct/dga-part2/)
- [securelist rotexy 2018](https://securelist.com/the-rotexy-mobile-trojan-banker-and-ransomware/88893/)
