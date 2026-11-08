# T1496.001 - Compute Hijacking

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1496 - Resource Hijacking](../README.md)

Adversaries may leverage the compute resources of co-opted systems to complete resource-intensive tasks, which may impact system and/or hosted service availability. 

One common purpose for [Compute Hijacking](https://attack.mitre.org/techniques/T1496/001) is to validate transactions of cryptocurrency networks and earn virtual currency. Adversaries may consume enough system resources to negatively impact and/or cause affected machines to become unresponsive.(Citation: Kaspersky Lazarus Under The Hood Blog 2017) Servers and cloud-based systems are common targets because of the high potential for available resources, but user endpoint systems may also be compromised and used for [Compute Hijacking](https://attack.mitre.org/techniques/T1496/001) and cryptocurrency mining.(Citation: CloudSploit - Unused AWS Regions) Containerized environments may also be targeted due to the ease of deployment via exposed APIs and the potential for scaling mining activities by deploying or compromising multiple containers within an environment or cluster.(Citation: Unit 42 Hildegard Malware)(Citation: Trend Micro Exposed Docker APIs)

Additionally, some cryptocurrency mining malware identify then kill off processes for competing malware to ensure it’s not competing for resources.(Citation: Trend Micro War of Crypto Miners)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1496/001)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [IaaS](../../../../Platforms/IaaS.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Containers](../../../../Platforms/Containers.md)

## Procedure examples

- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) deployed a Monero cryptocurrency mining tool in a victim’s environment.(Citation: FireEye APT41 Aug 2019)(Citation: apt41_mandiant) [FireEye APT41 Aug 2019](https://www.mandiant.com/sites/default/files/2022-02/rt-apt41-dual-operation.pdf)
- [G0108 - Blue Mockingbird](../../../../Threat%20Intelligence/Groups/G0108%20-%20Blue%20Mockingbird.md) — [Blue Mockingbird](https://attack.mitre.org/groups/G0108) has used XMRIG to mine cryptocurrency on victim systems.(Citation: RedCanary Mockingbird May 2020) [RedCanary Mockingbird May 2020](https://redcanary.com/blog/blue-mockingbird-cryptominer/)
- [S0486 - Bonadan](../../../../Threat%20Intelligence/Software/Malware/S0486%20-%20Bonadan.md) — [Bonadan](https://attack.mitre.org/software/S0486) can download an additional module which has a cryptocurrency mining extension.(Citation: ESET ForSSHe December 2018) [ESET ForSSHe December 2018](https://www.welivesecurity.com/wp-content/uploads/2018/12/ESET-The_Dark_Side_of_the_ForSSHe.pdf)
- [S0492 - CookieMiner](../../../../Threat%20Intelligence/Software/Malware/S0492%20-%20CookieMiner.md) — [CookieMiner](https://attack.mitre.org/software/S0492) has loaded coinmining software onto systems to mine for Koto cryptocurrency. (Citation: Unit42 CookieMiner Jan 2019) [Unit42 CookieMiner Jan 2019](https://unit42.paloaltonetworks.com/mac-malware-steals-cryptocurrency-exchanges-cookies/)
- [S1111 - DarkGate](../../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) can deploy follow-on cryptocurrency mining payloads.(Citation: Ensilo Darkgate 2018) [Ensilo Darkgate 2018](https://www.fortinet.com/blog/threat-research/enter-the-darkgate-new-cryptocurrency-mining-and-ransomware-campaign)
- [S0601 - Hildegard](../../../../Threat%20Intelligence/Software/Malware/S0601%20-%20Hildegard.md) — [Hildegard](https://attack.mitre.org/software/S0601) has used xmrig to mine cryptocurrency.(Citation: Unit 42 Hildegard Malware) [Unit 42 Hildegard Malware](https://unit42.paloaltonetworks.com/hildegard-malware-teamtnt/)
- [S0434 - Imminent Monitor](../../../../Threat%20Intelligence/Software/Tools/S0434%20-%20Imminent%20Monitor.md) — [Imminent Monitor](https://attack.mitre.org/software/S0434) has the capability to run a cryptocurrency miner on the victim machine.(Citation: Imminent Unit42 Dec2019) [Imminent Unit42 Dec2019](https://unit42.paloaltonetworks.com/imminent-monitor-a-rat-down-under/)
- [S0599 - Kinsing](../../../../Threat%20Intelligence/Software/Malware/S0599%20-%20Kinsing.md) — [Kinsing](https://attack.mitre.org/software/S0599) has created and run a Bitcoin cryptocurrency miner.(Citation: Aqua Kinsing April 2020)(Citation: Sysdig Kinsing November 2020) [Sysdig Kinsing November 2020](https://sysdig.com/blog/zoom-into-kinsing-kdevtmpfsi/) · [Aqua Kinsing April 2020](https://blog.aquasec.com/threat-alert-kinsing-malware-container-vulnerability)
- [S0451 - LoudMiner](../../../../Threat%20Intelligence/Software/Malware/S0451%20-%20LoudMiner.md) — [LoudMiner](https://attack.mitre.org/software/S0451) harvested system resources to mine cryptocurrency, using XMRig to mine Monero.(Citation: ESET LoudMiner June 2019) [ESET LoudMiner June 2019](https://www.welivesecurity.com/2019/06/20/loudminer-mining-cracked-vst-software/)
- [S0532 - Lucifer](../../../../Threat%20Intelligence/Software/Malware/S0532%20-%20Lucifer.md) — [Lucifer](https://attack.mitre.org/software/S0532) can use system resources to mine cryptocurrency, dropping XMRig to mine Monero.(Citation: Unit 42 Lucifer June 2020) [Unit 42 Lucifer June 2020](https://unit42.paloaltonetworks.com/lucifer-new-cryptojacking-and-ddos-hybrid-malware/)
- [G0106 - Rocke](../../../../Threat%20Intelligence/Groups/G0106%20-%20Rocke.md) — [Rocke](https://attack.mitre.org/groups/G0106) has distributed cryptomining malware.(Citation: Talos Rocke August 2018)(Citation: Unit 42 Rocke January 2019) [Talos Rocke August 2018](https://blog.talosintelligence.com/2018/08/rocke-champion-of-monero-miners.html) · [Unit 42 Rocke January 2019](https://unit42.paloaltonetworks.com/malware-used-by-rocke-group-evolves-to-evade-detection-by-cloud-security-products/)
- [C0045 - ShadowRay](../../../../Threat%20Intelligence/Campaigns/C0045%20-%20ShadowRay.md) — During [ShadowRay](https://attack.mitre.org/campaigns/C0045), threat actors leveraged graphics processing units (GPU) on compromised nodes for cryptocurrency mining.(Citation: Oligo ShadowRay Campaign MAR 2024) [Oligo ShadowRay Campaign MAR 2024](https://www.oligo.security/blog/shadowray-attack-ai-workloads-actively-exploited-in-the-wild)
- [S0468 - Skidmap](../../../../Threat%20Intelligence/Software/Malware/S0468%20-%20Skidmap.md) — [Skidmap](https://attack.mitre.org/software/S0468) is a kernel-mode rootkit used for cryptocurrency mining.(Citation: Trend Micro Skidmap) [Trend Micro Skidmap](https://blog.trendmicro.com/trendlabs-security-intelligence/skidmap-linux-malware-uses-rootkit-capabilities-to-hide-cryptocurrency-mining-payload/)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has deployed XMRig Docker images to mine cryptocurrency.(Citation: Lacework TeamTNT May 2021)(Citation: Cado Security TeamTNT Worm August 2020) [TeamTNT](https://attack.mitre.org/groups/G0139) has also infected Docker containers and Kubernetes clusters with XMRig, and used RainbowMiner and lolMiner for mining cryptocurrency.(Citation: Cisco Talos Intelligence Group) [Cado Security TeamTNT Worm August 2020](https://www.cadosecurity.com/team-tnt-the-first-crypto-mining-worm-to-steal-aws-credentials/) · [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/) · [Lacework TeamTNT May 2021](https://www.lacework.com/blog/taking-teamtnt-docker-images-offline)

## Detection strategies

- [DET0540 - Multi-Platform Behavioral Detection for Compute Hijacking](../../../../Defenses/Detection%20Strategies/DET0540%20-%20Multi-Platform%20Behavioral%20Detection%20for%20Compute%20Hijacking.md)

## Sources

- [Unit 42 Hildegard Malware](https://unit42.paloaltonetworks.com/hildegard-malware-teamtnt/)
- [CloudSploit - Unused AWS Regions](https://medium.com/cloudsploit/the-danger-of-unused-aws-regions-af0bf1b878fc)
- [Kaspersky Lazarus Under The Hood Blog 2017](https://securelist.com/lazarus-under-the-hood/77908/)
- [Trend Micro Exposed Docker APIs](https://www.trendmicro.com/en_us/research/19/e/infected-cryptocurrency-mining-containers-target-docker-hosts-with-exposed-apis-use-shodan-to-find-additional-victims.html)
- [Trend Micro War of Crypto Miners](https://www.trendmicro.com/en_us/research/20/i/war-of-linux-cryptocurrency-miners-a-battle-for-resources.html)
