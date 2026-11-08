# T1071 - Application Layer Protocol

[Enterprise](../../../README.md) / [Command and Control](../README.md)

Adversaries may communicate using OSI application layer protocols to avoid detection/network filtering by blending in with existing traffic. Commands to the remote system, and often the results of those commands, will be embedded within the protocol traffic between the client and server. 

Adversaries may utilize many different protocols, including those used for web browsing, transferring files, electronic mail, DNS, or publishing/subscribing. For connections that occur internally within an enclave (such as those between a proxy or pivot node and other nodes), commonly used protocols are SMB, SSH, or RDP.(Citation: Mandiant APT29 Eye Spy Email Nov 22)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1071)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md), [Network Devices](../../../Platforms/Network%20Devices.md), [ESXi](../../../Platforms/ESXi.md)

## Sub-techniques

- [T1071.004 - DNS](T1071.004%20-%20DNS/README.md)
- [T1071.002 - File Transfer Protocols](T1071.002%20-%20File%20Transfer%20Protocols/README.md)
- [T1071.003 - Mail Protocols](T1071.003%20-%20Mail%20Protocols/README.md)
- [T1071.005 - Publish/Subscribe Protocols](T1071.005%20-%20Publish%20-%20Subscribe%20Protocols/README.md)
- [T1071.001 - Web Protocols](T1071.001%20-%20Web%20Protocols/README.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Use network appliances to filter ingress or egress traffic and perform protocol-based filtering. Configure software on endpoints to filter network traffic.
- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level.

## Procedure examples

- [S0660 - Clambling](../../../Threat%20Intelligence/Software/Malware/S0660%20-%20Clambling.md) — [Clambling](https://attack.mitre.org/software/S0660) has the ability to use Telnet for communication.(Citation: Trend Micro DRBControl February 2020) [Trend Micro DRBControl February 2020](https://documents.trendmicro.com/assets/white_papers/wp-uncovering-DRBcontrol.pdf)
- [S0038 - Duqu](../../../Threat%20Intelligence/Software/Malware/S0038%20-%20Duqu.md) — [Duqu](https://attack.mitre.org/software/S0038) uses a custom command and control protocol that communicates over commonly used ports, and is frequently encapsulated by application layer protocols.(Citation: Symantec W32.Duqu) [Symantec W32.Duqu](https://web.archive.org/web/20111213083345/https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf)
- [C0041 - FrostyGoop Incident](../../../Threat%20Intelligence/Campaigns/C0041%20-%20FrostyGoop%20Incident.md) — During [FrostyGoop Incident](https://attack.mitre.org/campaigns/C0041), the adversary initiated Layer Two Tunnelling Protocol (L2TP) connections to Moscow-based IP addresses.(Citation: Dragos FROSTYGOOP 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [S0601 - Hildegard](../../../Threat%20Intelligence/Software/Malware/S0601%20-%20Hildegard.md) — [Hildegard](https://attack.mitre.org/software/S0601) has used an IRC channel for C2 communications.(Citation: Unit 42 Hildegard Malware) [Unit 42 Hildegard Malware](https://unit42.paloaltonetworks.com/hildegard-malware-teamtnt/)
- [G1032 - INC Ransom](../../../Threat%20Intelligence/Groups/G1032%20-%20INC%20Ransom.md) — [INC Ransom](https://attack.mitre.org/groups/G1032) has used valid accounts over RDP to connect to targeted systems.(Citation: Huntress INC Ransom Group August 2023) [Huntress INC Ransom Group August 2023](https://www.huntress.com/blog/investigating-new-inc-ransom-group-activity)
- [S0532 - Lucifer](../../../Threat%20Intelligence/Software/Malware/S0532%20-%20Lucifer.md) — [Lucifer](https://attack.mitre.org/software/S0532) can use the Stratum protocol on port 10001 for communication between the cryptojacking bot and the mining server.(Citation: Unit 42 Lucifer June 2020) [Unit 42 Lucifer June 2020](https://unit42.paloaltonetworks.com/lucifer-new-cryptojacking-and-ddos-hybrid-malware/)
- [G0059 - Magic Hound](../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) malware has used IRC for C2.(Citation: Unit 42 Magic Hound Feb 2017)(Citation: DFIR Phosphorus November 2021) [DFIR Phosphorus November 2021](https://thedfirreport.com/2021/11/15/exchange-exploit-leads-to-domain-wide-ransomware/) · [Unit 42 Magic Hound Feb 2017](https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/)
- [S0034 - NETEAGLE](../../../Threat%20Intelligence/Software/Malware/S0034%20-%20NETEAGLE.md) — Adversaries can also use [NETEAGLE](https://attack.mitre.org/software/S0034) to establish an RDP connection with a controller over TCP/7519.
- [S1147 - Nightdoor](../../../Threat%20Intelligence/Software/Malware/S1147%20-%20Nightdoor.md) — [Nightdoor](https://attack.mitre.org/software/S1147) uses TCP and UDP communication for command and control traffic.(Citation: ESET EvasivePanda 2024)(Citation: Symantec Daggerfly 2024) [ESET EvasivePanda 2024](https://www.welivesecurity.com/en/eset-research/evasive-panda-leverages-monlam-festival-target-tibetans/) · [Symantec Daggerfly 2024](https://symantec-enterprise-blogs.security.com/threat-intelligence/daggerfly-espionage-updated-toolset)
- [G1059 - NIMBUS MANTICORE](../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has leveraged reverse SSH shells for command and control.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [S1084 - QUIETEXIT](../../../Threat%20Intelligence/Software/Malware/S1084%20-%20QUIETEXIT.md) — [QUIETEXIT](https://attack.mitre.org/software/S1084) can use an inverse negotiated SSH connection as part of its C2.(Citation: Mandiant APT29 Eye Spy Email Nov 22) [Mandiant APT29 Eye Spy Email Nov 22](https://www.mandiant.com/resources/blog/unc3524-eye-spy-email)
- [S1130 - Raspberry Robin](../../../Threat%20Intelligence/Software/Malware/S1130%20-%20Raspberry%20Robin.md) — [Raspberry Robin](https://attack.mitre.org/software/S1130) is capable of contacting the TOR network for delivering second-stage payloads.(Citation: RedCanary RaspberryRobin 2022)(Citation: TrendMicro RaspberryRobin 2022)(Citation: HP RaspberryRobin 2024) [TrendMicro RaspberryRobin 2022](https://www.trendmicro.com/en_us/research/22/l/raspberry-robin-malware-targets-telecom-governments.html) · [RedCanary RaspberryRobin 2022](https://redcanary.com/blog/threat-intelligence/raspberry-robin/) · [HP RaspberryRobin 2024](https://threatresearch.ext.hp.com/raspberry-robin-now-spreading-through-windows-script-files/)
- [G0106 - Rocke](../../../Threat%20Intelligence/Groups/G0106%20-%20Rocke.md) — [Rocke](https://attack.mitre.org/groups/G0106) issued wget requests from infected systems to the C2.(Citation: Talos Rocke August 2018) [Talos Rocke August 2018](https://blog.talosintelligence.com/2018/08/rocke-champion-of-monero-miners.html)
- [S0623 - Siloscape](../../../Threat%20Intelligence/Software/Malware/S0623%20-%20Siloscape.md) — [Siloscape](https://attack.mitre.org/software/S0623) connects to an IRC server for C2.(Citation: Unit 42 Siloscape Jun 2021) [Unit 42 Siloscape Jun 2021](https://unit42.paloaltonetworks.com/siloscape/)
- [S0633 - Sliver](../../../Threat%20Intelligence/Software/Tools/S0633%20-%20Sliver.md) — [Sliver](https://attack.mitre.org/software/S0633) can utilize the Wireguard VPN protocol for command and control.(Citation: Cybereason Sliver Undated) [Cybereason Sliver Undated](https://www.cybereason.com/blog/sliver-c2-leveraged-by-many-threat-actors)
- [G0139 - TeamTNT](../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has used an IRC bot for C2 communications.(Citation: Trend Micro TeamTNT) [Trend Micro TeamTNT](https://documents.trendmicro.com/assets/white_papers/wp-tracking-the-activities-of-teamTNT.pdf)
- [G1047 - Velvet Ant](../../../Threat%20Intelligence/Groups/G1047%20-%20Velvet%20Ant.md) — [Velvet Ant](https://attack.mitre.org/groups/G1047) has used reverse SSH tunnels to communicate to victim devices.(Citation: Sygnia VelvetAnt 2024A) [Sygnia VelvetAnt 2024A](https://www.sygnia.co/blog/china-nexus-threat-group-velvet-ant/)

## Detection strategies

- [DET0444 - Detection of Command and Control Over Application Layer Protocols](../../../Defenses/Detection%20Strategies/DET0444%20-%20Detection%20of%20Command%20and%20Control%20Over%20Application%20Layer%20Protocols.md)

## Sources

- [University of Birmingham C2](https://arxiv.org/pdf/1408.1136)
- [Mandiant APT29 Eye Spy Email Nov 22](https://www.mandiant.com/resources/blog/unc3524-eye-spy-email)
