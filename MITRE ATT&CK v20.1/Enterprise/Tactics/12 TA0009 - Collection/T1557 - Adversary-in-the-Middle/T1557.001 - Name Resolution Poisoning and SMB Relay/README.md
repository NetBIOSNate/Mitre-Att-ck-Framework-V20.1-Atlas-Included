# T1557.001 - Name Resolution Poisoning and SMB Relay

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1557 - Adversary-in-the-Middle](../README.md)

By responding to LLMNR/NBT-NS/mDNS network traffic, adversaries may spoof an authoritative source for name resolution to force communication with an adversary controlled system.(Citation: BlackCat ransomware) This activity may be used to collect or relay authentication materials. 

Link-Local Multicast Name Resolution (LLMNR) and NetBIOS Name Service (NBT-NS) are Microsoft Windows components that serve as alternate methods of host identification. LLMNR is based upon the Domain Name System (DNS) format and allows hosts on the same local link to perform name resolution for other hosts. NBT-NS identifies systems on a local network by their NetBIOS name.(Citation: Wikipedia LLMNR)(Citation: TechNet NetBIOS)

Multicast Domain Name System(mDNS) is a zero-configuration service used to resolve hostnames to IP addresses with “.local” as a top-level domain. MDNS is based upon Domain Name System (DNS) format and allows hosts on the same network segment to perform name resolution for other hosts, using multicast.(Citation: mDNS RFC)

Adversaries can spoof an authoritative source for name resolution on a victim network by responding to LLMNR (UDP 5355)/NBT-NS (UDP 137)/mDNS (UDP 5353) traffic as if they know the identity of the requested host, effectively poisoning the service so that the victims will communicate with the adversary controlled system. If the requested host belongs to a resource that requires identification/authentication, the username and NTLMv2 hash will then be sent to the adversary controlled system. The adversary can then collect the hash information sent over the wire through tools that monitor the ports for traffic or through [Network Sniffing](https://attack.mitre.org/techniques/T1040) and crack the hashes offline through [Brute Force](https://attack.mitre.org/techniques/T1110) to obtain the plaintext passwords.

In some cases where an adversary has access to a system that is in the authentication path between systems or when automated scans that use credentials attempt to authenticate to an adversary controlled system, the NTLMv1/v2 hashes can be intercepted and relayed to access and execute code against a target system. The relay step can happen in conjunction with poisoning but may also be independent of it.(Citation: byt3bl33d3r NTLM Relaying)(Citation: Secure Ideas SMB Relay) Additionally, adversaries may encapsulate the NTLMv1/v2 hashes into various other protocols, such as LDAP, MSSQL and HTTP, to expand and use multiple services with the valid NTLM response. 

Several tools may be used to poison name services within local networks such as NBNSpoof, Metasploit, and [Responder](https://attack.mitre.org/software/S0174).(Citation: GitHub NBNSpoof)(Citation: Rapid7 LLMNR Spoofer)(Citation: GitHub Responder)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1557/001)

**Tactics**  [Credential Access](../../../09%20TA0006%20-%20Credential%20Access/README.md), [Collection](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) can use Inveigh to conduct name service poisoning for credential theft and associated relay attacks.(Citation: Github PowerShell Empire)(Citation: GitHub Inveigh) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire) · [GitHub Inveigh](https://github.com/Kevin-Robertson/Inveigh)
- [S0357 - Impacket](../../../../Threat%20Intelligence/Software/Tools/S0357%20-%20Impacket.md) — [Impacket](https://attack.mitre.org/software/S0357) modules like ntlmrelayx and smbrelayx can be used in conjunction with [Network Sniffing](https://attack.mitre.org/techniques/T1040) and [Name Resolution Poisoning and SMB Relay](https://attack.mitre.org/techniques/T1557/001) to gather NetNTLM credentials for [Brute Force](https://attack.mitre.org/techniques/T1110) or relay attacks that can gain code execution.(Citation: Impacket Tools) [Impacket Tools](https://www.secureauth.com/labs/open-source-tools/impacket)
- [G0032 - Lazarus Group](../../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) executed [Responder](https://attack.mitre.org/software/S0174) using the command <code>[Responder file path] -i [IP address] -rPv</code> on a compromised host to harvest credentials and move laterally.(Citation: Kaspersky ThreatNeedle Feb 2021) [Kaspersky ThreatNeedle Feb 2021](https://securelist.com/lazarus-threatneedle/100803/)
- [S0378 - PoshC2](../../../../Threat%20Intelligence/Software/Tools/S0378%20-%20PoshC2.md) — [PoshC2](https://attack.mitre.org/software/S0378) can use Inveigh to conduct name service poisoning for credential theft and associated relay attacks.(Citation: GitHub PoshC2) [GitHub PoshC2](https://github.com/nettitude/PoshC2_Python)
- [S0192 - Pupy](../../../../Threat%20Intelligence/Software/Tools/S0192%20-%20Pupy.md) — [Pupy](https://attack.mitre.org/software/S0192) can sniff plaintext network credentials and use NBNS Spoofing to poison name services.(Citation: GitHub Pupy) [GitHub Pupy](https://github.com/n1nj4sec/pupy)
- [S0174 - Responder](../../../../Threat%20Intelligence/Software/Tools/S0174%20-%20Responder.md) — [Responder](https://attack.mitre.org/software/S0174) is used to poison name services to gather hashes and credentials from systems within a local network.(Citation: GitHub Responder) [GitHub Responder](https://github.com/SpiderLabs/Responder)
- [G0102 - Wizard Spider](../../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has used the Invoke-Inveigh PowerShell cmdlets, likely for name service poisoning.(Citation: FireEye KEGTAP SINGLEMALT October 2020) [FireEye KEGTAP SINGLEMALT October 2020](https://www.fireeye.com/blog/threat-research/2020/10/kegtap-and-singlemalt-with-a-ransomware-chaser.html)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable LLMNR, mDNS, and NetBIOS in local computer security settings or by group policy if they are not needed within an environment. (Citation: ADSecurity Windows Secure Baseline) [ADSecurity Windows Secure Baseline](https://adsecurity.org/?p=3299)
- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Use host-based security software to block LLMNR/NetBIOS/mDNS traffic. Enabling SMB Signing can stop NTLMv2 relay attacks.(Citation: byt3bl33d3r NTLM Relaying)(Citation: Secure Ideas SMB Relay)(Citation: Microsoft SMB Packet Signing) [Secure Ideas SMB Relay](https://blog.secureideas.com/2018/04/ever-run-a-relay-why-smb-relays-should-be-on-your-mind.html) · [Microsoft SMB Packet Signing](https://docs.microsoft.com/en-us/previous-versions/system-center/operations-manager-2005/cc180803%28v=technet.10%29) · [byt3bl33d3r NTLM Relaying](https://byt3bl33d3r.github.io/practical-guide-to-ntlm-relaying-in-2017-aka-getting-a-foothold-in-under-5-minutes.html)
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that can identify traffic patterns indicative of AiTM activity can be used to mitigate activity at the network level.
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Network segmentation can be used to isolate infrastructure components that do not require broad network access. This may mitigate, or at least alleviate, the scope of AiTM activity.

## Detection strategies

- [DET0462 - Detect LLMNR/NBT-NS Poisoning and SMB Relay on Windows](../../../../Defenses/Detection%20Strategies/DET0462%20-%20Detect%20LLMNR%20-%20NBT-NS%20Poisoning%20and%20SMB%20Relay%20on%20Windows.md)

## Sources

- [Rapid7 LLMNR Spoofer](https://www.rapid7.com/db/modules/auxiliary/spoof/llmnr/llmnr_response)
- [GitHub Responder](https://github.com/SpiderLabs/Responder)
- [Secure Ideas SMB Relay](https://blog.secureideas.com/2018/04/ever-run-a-relay-why-smb-relays-should-be-on-your-mind.html)
- [BlackCat ransomware](https://www.trendmicro.com/en_us/research/22/d/an-investigation-of-the-blackcat-ransomware.html)
- [TechNet NetBIOS](https://technet.microsoft.com/library/cc958811.aspx)
- [GitHub NBNSpoof](https://github.com/nomex/nbnspoof)
- [mDNS RFC](https://datatracker.ietf.org/doc/html/rfc6762)
- [byt3bl33d3r NTLM Relaying](https://byt3bl33d3r.github.io/practical-guide-to-ntlm-relaying-in-2017-aka-getting-a-foothold-in-under-5-minutes.html)
- [Wikipedia LLMNR](https://en.wikipedia.org/wiki/Link-Local_Multicast_Name_Resolution)
