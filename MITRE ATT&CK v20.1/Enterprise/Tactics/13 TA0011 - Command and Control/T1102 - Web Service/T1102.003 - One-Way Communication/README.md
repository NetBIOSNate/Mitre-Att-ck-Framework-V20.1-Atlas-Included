# T1102.003 - One-Way Communication

[Enterprise](../../../../README.md) / [Command and Control](../../README.md) / [T1102 - Web Service](../README.md)

Adversaries may use an existing, legitimate external Web service as a means for sending commands to a compromised system without receiving return output over the Web service channel. Compromised systems may leverage popular websites and social media to host command and control (C2) instructions. Those infected systems may opt to send the output from those commands back over a different C2 channel, including to another distinct Web service. Alternatively, compromised systems may return no output at all in cases where adversaries want to send instructions to systems and do not want a response.

Popular websites and social media acting as a mechanism for C2 may give a significant amount of cover due to the likelihood that hosts within a network are already communicating with them prior to a compromise. Using common services, such as those offered by Google or Twitter, makes it easier for adversaries to hide in expected noise. Web service providers commonly use SSL/TLS encryption, giving adversaries an added level of protection.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1102/003)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md), [ESXi](../../../../Platforms/ESXi.md)

## Procedure examples

- [C0046 - ArcaneDoor](../../../../Threat%20Intelligence/Campaigns/C0046%20-%20ArcaneDoor.md) — [ArcaneDoor](https://attack.mitre.org/campaigns/C0046) utilized HTTP command and control traffic where commands are intercepted from HTTP traffic to the device, parsed for appropriate identifiers and commands, and then executed.(Citation: Cisco ArcaneDoor 2024) [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [S0568 - EVILNUM](../../../../Threat%20Intelligence/Software/Malware/S0568%20-%20EVILNUM.md) — [EVILNUM](https://attack.mitre.org/software/S0568) has used a one-way communication method via GitLab and Digital Point to perform C2.(Citation: Prevailion EvilNum May 2020) [Prevailion EvilNum May 2020](https://web.archive.org/web/20221209052853/https://www.prevailion.com/phantom-in-the-command-shell-2/)
- [G0047 - Gamaredon Group](../../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has used Telegram Messenger content to discover the IP address for C2 communications.(Citation: unit42_gamaredon_dec2022) [unit42_gamaredon_dec2022](https://unit42.paloaltonetworks.com/trident-ursa/)
- [S0037 - HAMMERTOSS](../../../../Threat%20Intelligence/Software/Malware/S0037%20-%20HAMMERTOSS.md) — The "tDiscoverer" variant of [HAMMERTOSS](https://attack.mitre.org/software/S0037) establishes a C2 channel by downloading resources from Web services like Twitter and GitHub. [HAMMERTOSS](https://attack.mitre.org/software/S0037) binaries contain an algorithm that generates a different Twitter handle for the malware to check for instructions every day.(Citation: FireEye APT29) [FireEye APT29](https://services.google.com/fh/files/misc/rpt-apt29-hammertoss-stealthy-tactics-define-en.pdf)
- [G0065 - Leviathan](../../../../Threat%20Intelligence/Groups/G0065%20-%20Leviathan.md) — [Leviathan](https://attack.mitre.org/groups/G0065) has received C2 instructions from user profiles created on legitimate websites such as Github and TechNet.(Citation: FireEye Periscope March 2018) [FireEye Periscope March 2018](https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html)
- [S0455 - Metamorfo](../../../../Threat%20Intelligence/Software/Malware/S0455%20-%20Metamorfo.md) — [Metamorfo](https://attack.mitre.org/software/S0455) has downloaded a zip file for execution on the system.(Citation: Medium Metamorfo Apr 2020)(Citation: FireEye Metamorfo Apr 2018)(Citation: Fortinet Metamorfo Feb 2020) [Medium Metamorfo Apr 2020](https://medium.com/@chenerlich/the-avast-abuser-metamorfo-banking-malware-hides-by-abusing-avast-executable-ac9b8b392767) · [FireEye Metamorfo Apr 2018](https://www.fireeye.com/blog/threat-research/2018/04/metamorfo-campaign-targeting-brazilian-users.html) · [Fortinet Metamorfo Feb 2020](https://www.fortinet.com/blog/threat-research/another-metamorfo-variant-targeting-customers-of-financial-institutions)
- [S0052 - OnionDuke](../../../../Threat%20Intelligence/Software/Malware/S0052%20-%20OnionDuke.md) — [OnionDuke](https://attack.mitre.org/software/S0052) uses Twitter as a backup C2.(Citation: F-Secure The Dukes) [F-Secure The Dukes](https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf)
- [S1210 - Sagerunex](../../../../Threat%20Intelligence/Software/Malware/S1210%20-%20Sagerunex.md) — [Sagerunex](https://attack.mitre.org/software/S1210) has used web services such as Twitter for command and control purposes.(Citation: Cisco LotusBlossom 2025) [Cisco LotusBlossom 2025](https://blog.talosintelligence.com/lotus-blossom-espionage-group/)
- [S1164 - UPSTYLE](../../../../Threat%20Intelligence/Software/Malware/S1164%20-%20UPSTYLE.md) — [UPSTYLE](https://attack.mitre.org/software/S1164) parses encoded commands from error logs after attempting to resolve a non-existing webpage from the command and control server.(Citation: Volexity UPSTYLE 2024) [Volexity UPSTYLE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)

## Detection strategies

- [DET0581 - Detect One-Way Web Service Command Channels](../../../../Defenses/Detection%20Strategies/DET0581%20-%20Detect%20One-Way%20Web%20Service%20Command%20Channels.md)

## Mitigations

- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level.
- [M1021 - Restrict Web-Based Content](../../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — Web proxies can be used to enforce external network communication policy that prevents use of unauthorized external services.

## Sources

- [University of Birmingham C2](https://arxiv.org/pdf/1408.1136)
