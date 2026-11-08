# T1205.001 - Port Knocking

[Enterprise](../../../../README.md) / [Command and Control](../../README.md) / [T1205 - Traffic Signaling](../README.md)

Adversaries may use port knocking to hide open ports used for persistence or command and control. To enable a port, an adversary sends a series of attempted connections to a predefined sequence of closed ports. After the sequence is completed, opening a port is often accomplished by the host based firewall, but could also be implemented by custom software.

This technique has been observed both for the dynamic opening of a listening port as well as the initiating of a connection to a listening server on a different system.

The observation of the signal packets to trigger the communication can be conducted through different methods. One means, originally implemented by Cd00r,(Citation: Hartrell cd00r 2002) is to use the libpcap libraries to sniff for the packets in question. Another method leverages raw sockets, which enables the malware to use ports that are already open for use by other programs.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1205/001)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md), [Command and Control](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Mitigation of some variants of this technique could be achieved through the use of stateful firewalls, depending upon how it is implemented.

## Procedure examples

- [S1204 - cd00r](../../../../Threat%20Intelligence/Software/Malware/S1204%20-%20cd00r.md) — [cd00r](https://attack.mitre.org/software/S1204) can monitor for a single TCP-SYN packet to be sent in series to a configurable set of ports (200, 80, 22, 53 and 3 in the original code) before opening a port for communication.(Citation: Hartrell cd00r 2002)(Citation: Lumen J-Magic JAN 2025) [Lumen J-Magic JAN 2025](https://blog.lumen.com/the-j-magic-show-magic-packets-and-where-to-find-them/) · [Hartrell cd00r 2002](https://www.giac.org/paper/gcih/342/handle-cd00r-invisible-backdoor/103631)
- [S1060 - Mafalda](../../../../Threat%20Intelligence/Software/Malware/S1060%20-%20Mafalda.md) — [Mafalda](https://attack.mitre.org/software/S1060) can use port-knocking to authenticate itself to another implant called Cryshell to establish an indirect connection to the C2 server.(Citation: SentinelLabs Metador Sept 2022)(Citation: SentinelLabs Metador Technical Appendix Sept 2022) [SentinelLabs Metador Sept 2022](https://assets.sentinelone.com/sentinellabs22/metador#page=1) · [SentinelLabs Metador Technical Appendix Sept 2022](https://docs.google.com/document/d/1e9ZTW9b71YwFWS_18ZwDAxa-cYbV8q1wUefmKZLYVsA/edit#heading=h.lmnbtht1ikzm)
- [S1059 - metaMain](../../../../Threat%20Intelligence/Software/Malware/S1059%20-%20metaMain.md) — [metaMain](https://attack.mitre.org/software/S1059) has authenticated itself to a different implant, Cryshell, through a port knocking and handshake procedure.(Citation: SentinelLabs Metador Sept 2022) [SentinelLabs Metador Sept 2022](https://assets.sentinelone.com/sentinellabs22/metador#page=1)
- [G0056 - PROMETHIUM](../../../../Threat%20Intelligence/Groups/G0056%20-%20PROMETHIUM.md) — [PROMETHIUM](https://attack.mitre.org/groups/G0056) has used a script that configures the knockd service and firewall to only accept C2 connections from systems that use a specified sequence of knock ports.(Citation: Bitdefender StrongPity June 2020) [Bitdefender StrongPity June 2020](https://www.bitdefender.com/files/News/CaseStudies/study/353/Bitdefender-Whitepaper-StrongPity-APT.pdf)
- [S1219 - REPTILE](../../../../Threat%20Intelligence/Software/Malware/S1219%20-%20REPTILE.md) — [REPTILE](https://attack.mitre.org/software/S1219) has the ability to control compromised endpoints via port knocking.(Citation: Google Cloud Mandiant UNC3886 2024) [Google Cloud Mandiant UNC3886 2024](https://cloud.google.com/blog/topics/threat-intelligence/uncovering-unc3886-espionage-operations)
- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) maintained persistence on FortiGate Firewalls through ICMP port knocking.(Citation: Mandiant Fortinet Zero Day) [Mandiant Fortinet Zero Day](https://www.mandiant.com/resources/blog/fortinet-malware-ecosystem)

## Detection strategies

- [DET0302 - Port-knock → rule/daemon change → first successful connect (T1205.001)](../../../../Defenses/Detection%20Strategies/DET0302%20-%20Port-knock%20%E2%86%92%20rule%20-%20daemon%20change%20%E2%86%92%20first%20successful%20connect%20%28T1205.001%29.md)

## Sources

- [Hartrell cd00r 2002](https://www.giac.org/paper/gcih/342/handle-cd00r-invisible-backdoor/103631)
