# T1573 - Encrypted Channel

[Enterprise](../../../README.md) / [Command and Control](../README.md)

Adversaries may employ an encryption algorithm to conceal command and control traffic rather than relying on any inherent protections provided by a communication protocol. Despite the use of a secure algorithm, these implementations may be vulnerable to reverse engineering if secret keys are encoded and/or generated within malware samples/configuration files.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1573)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1573.002 - Asymmetric Cryptography](T1573.002%20-%20Asymmetric%20Cryptography/README.md)
- [T1573.001 - Symmetric Cryptography](T1573.001%20-%20Symmetric%20Cryptography/README.md)

## Procedure examples

- [G0016 - APT29](../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has used multiple layers of encryption within malware to protect C2 communication.(Citation: Secureworks IRON HEMLOCK Profile) [Secureworks IRON HEMLOCK Profile](http://www.secureworks.com/research/threat-profiles/iron-hemlock)
- [G1002 - BITTER](../../../Threat%20Intelligence/Groups/G1002%20-%20BITTER.md) — [BITTER](https://attack.mitre.org/groups/G1002) has encrypted their C2 communications.(Citation: Forcepoint BITTER Pakistan Oct 2016) [Forcepoint BITTER Pakistan Oct 2016](https://www.forcepoint.com/blog/x-labs/bitter-targeted-attack-against-pakistan)
- [S0631 - Chaes](../../../Threat%20Intelligence/Software/Malware/S0631%20-%20Chaes.md) — [Chaes](https://attack.mitre.org/software/S0631) has used encryption for its C2 channel.(Citation: Cybereason Chaes Nov 2020) [Cybereason Chaes Nov 2020](https://www.cybereason.com/hubfs/dam/collateral/reports/11-2020-Chaes-e-commerce-malware-research.pdf)
- [S0498 - Cryptoistic](../../../Threat%20Intelligence/Software/Malware/S0498%20-%20Cryptoistic.md) — [Cryptoistic](https://attack.mitre.org/software/S0498) can engage in encrypted communications with C2.(Citation: SentinelOne Lazarus macOS July 2020) [SentinelOne Lazarus macOS July 2020](https://www.sentinelone.com/blog/four-distinct-families-of-lazarus-malware-target-apples-macos-platform/)
- [S0367 - Emotet](../../../Threat%20Intelligence/Software/Malware/S0367%20-%20Emotet.md) — [Emotet](https://attack.mitre.org/software/S0367) has encrypted data before sending to the C2 server.(Citation: Fortinet Emotet May 2017) [Fortinet Emotet May 2017](https://www.fortinet.com/blog/threat-research/deep-analysis-of-new-emotet-variant-part-1.html)
- [S0032 - gh0st RAT](../../../Threat%20Intelligence/Software/Malware/S0032%20-%20gh0st%20RAT.md) — [gh0st RAT](https://attack.mitre.org/software/S0032) has encrypted TCP communications to evade detection.(Citation: Gh0stRAT ATT March 2019) [Gh0stRAT ATT March 2019](https://cybersecurity.att.com/blogs/labs-research/the-odd-case-of-a-gh0strat-variant)
- [S1198 - Gomir](../../../Threat%20Intelligence/Software/Malware/S1198%20-%20Gomir.md) — [Gomir](https://attack.mitre.org/software/S1198) uses a custom encryption algorithm for content sent to command and control infrastructure.(Citation: Symantec Troll Stealer 2024) [Symantec Troll Stealer 2024](https://www.security.com/threat-intelligence/springtail-kimsuky-backdoor-espionage)
- [C0035 - KV Botnet Activity](../../../Threat%20Intelligence/Campaigns/C0035%20-%20KV%20Botnet%20Activity.md) — [KV Botnet Activity](https://attack.mitre.org/campaigns/C0035) command and control activity includes transmission of an RSA public key in communication from the server, but this is followed by subsequent negotiation stages that represent a form of handshake similar to TLS negotiation.(Citation: Lumen KVBotnet 2023) [Lumen KVBotnet 2023](https://blog.lumen.com/routers-roasting-on-an-open-firewall-the-kv-botnet-investigation/)
- [S0681 - Lizar](../../../Threat%20Intelligence/Software/Malware/S0681%20-%20Lizar.md) — [Lizar](https://attack.mitre.org/software/S0681) can support encrypted communications between the client and server.(Citation: Threatpost Lizar May 2021)(Citation: BiZone Lizar May 2021)(Citation: Cocomazzi FIN7 Reboot) [BiZone Lizar May 2021](https://bi-zone.medium.com/from-pentest-to-apt-attack-cybercriminal-group-fin7-disguises-its-malware-as-an-ethical-hackers-c23c9a75e319) · [Cocomazzi FIN7 Reboot](https://www.sentinelone.com/labs/fin7-reboot-cybercrime-gang-enhances-ops-with-new-edr-bypasses-and-automated-attacks/) · [Threatpost Lizar May 2021](https://threatpost.com/fin7-backdoor-ethical-hacking-tool/166194/)
- [S1016 - MacMa](../../../Threat%20Intelligence/Software/Malware/S1016%20-%20MacMa.md) — [MacMa](https://attack.mitre.org/software/S1016) has used TLS encryption to initialize a custom protocol for C2 communications.(Citation: ESET DazzleSpy Jan 2022) [ESET DazzleSpy Jan 2022](https://www.welivesecurity.com/2022/01/25/watering-hole-deploys-new-macos-malware-dazzlespy-asia/)
- [G0059 - Magic Hound](../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has used an encrypted http proxy in C2 communications.(Citation: DFIR Phosphorus November 2021) [DFIR Phosphorus November 2021](https://thedfirreport.com/2021/11/15/exchange-exploit-leads-to-domain-wide-ransomware/)
- [S0198 - NETWIRE](../../../Threat%20Intelligence/Software/Malware/S0198%20-%20NETWIRE.md) — [NETWIRE](https://attack.mitre.org/software/S0198) can encrypt C2 communications.(Citation: Red Canary NETWIRE January 2020) [Red Canary NETWIRE January 2020](https://redcanary.com/blog/netwire-remote-access-trojan-on-linux/)
- [S1012 - PowerLess](../../../Threat%20Intelligence/Software/Malware/S1012%20-%20PowerLess.md) — [PowerLess](https://attack.mitre.org/software/S1012) can use an encrypted channel for C2 communications.(Citation: Cybereason PowerLess February 2022) [Cybereason PowerLess February 2022](https://www.cybereason.com/blog/research/powerless-trojan-iranian-apt-phosphorus-adds-new-powershell-backdoor-for-espionage)
- [S1046 - PowGoop](../../../Threat%20Intelligence/Software/Malware/S1046%20-%20PowGoop.md) — [PowGoop](https://attack.mitre.org/software/S1046) can receive encrypted commands from C2.(Citation: DHS CISA AA22-055A MuddyWater February 2022) [DHS CISA AA22-055A MuddyWater February 2022](https://www.cisa.gov/uscert/ncas/alerts/aa22-055a)
- [S0662 - RCSession](../../../Threat%20Intelligence/Software/Malware/S0662%20-%20RCSession.md) — [RCSession](https://attack.mitre.org/software/S0662) can use an encrypted beacon to check in with C2.(Citation: Secureworks BRONZE PRESIDENT December 2019) [Secureworks BRONZE PRESIDENT December 2019](https://www.secureworks.com/research/bronze-president-targets-ngos)
- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) used cryptcat binaries to encrypt their traffic.(Citation: FireEye TEMP.Veles 2018) [FireEye TEMP.Veles 2018](https://web.archive.org/web/20190202205824/https://www.fireeye.com/blog/threat-research/2018/10/triton-attribution-russian-government-owned-lab-most-likely-built-tools.html)
- [G0081 - Tropic Trooper](../../../Threat%20Intelligence/Groups/G0081%20-%20Tropic%20Trooper.md) — [Tropic Trooper](https://attack.mitre.org/groups/G0081) has encrypted traffic with the C2 to prevent network detection.(Citation: TrendMicro Tropic Trooper May 2020) [TrendMicro Tropic Trooper May 2020](https://documents.trendmicro.com/assets/Tech-Brief-Tropic-Trooper-s-Back-USBferry-Attack-Targets-Air-gapped-Environments.pdf)

## Detection strategies

- [DET0273 - Detection Strategy for Encrypted Channel across OS Platforms](../../../Defenses/Detection%20Strategies/DET0273%20-%20Detection%20Strategy%20for%20Encrypted%20Channel%20across%20OS%20Platforms.md)

## Mitigations

- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level.
- [M1020 - SSL/TLS Inspection](../../../Defenses/Mitigations/M1020%20-%20SSL%20-%20TLS%20Inspection.md) — SSL/TLS inspection can be used to see the contents of encrypted sessions to look for network-based indicators of malware communication protocols.

## Sources

- [SANS Decrypting SSL](http://www.sans.org/reading-room/whitepapers/analyst/finding-hidden-threats-decrypting-ssl-34840)
- [SEI SSL Inspection Risks](https://insights.sei.cmu.edu/cert/2015/03/the-risks-of-ssl-inspection.html)
- [University of Birmingham C2](https://arxiv.org/pdf/1408.1136)
