# T1584.008 - Network Devices

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1584 - Compromise Infrastructure](../README.md)

Adversaries may compromise third-party network devices that can be used during targeting. Network devices, such as small office/home office (SOHO) routers, may be compromised where the adversary's ultimate goal is not [Initial Access](https://attack.mitre.org/tactics/TA0001) to that environment, but rather to leverage these devices to support additional targeting.

Once an adversary has control, compromised network devices can be used to launch additional operations, such as hosting payloads for [Phishing](https://attack.mitre.org/techniques/T1566) campaigns (i.e., [Link Target](https://attack.mitre.org/techniques/T1608/005)) or enabling the required access to execute [Content Injection](https://attack.mitre.org/techniques/T1659) operations. Adversaries may also be able to harvest reusable credentials (i.e., [Valid Accounts](https://attack.mitre.org/techniques/T1078)) from compromised network devices.

Adversaries often target Internet-facing edge devices and related network appliances that specifically do not support robust host-based defenses.(Citation: Mandiant Fortinet Zero Day)(Citation: Wired Russia Cyberwar)

Compromised network devices may be used to support subsequent [Command and Control](https://attack.mitre.org/tactics/TA0011) activity, such as [Hide Infrastructure](https://attack.mitre.org/techniques/T1665) through an established [Proxy](https://attack.mitre.org/techniques/T1090) and/or [Botnet](https://attack.mitre.org/techniques/T1584/005) network.(Citation: Justice GRU 2024)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1584/008)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used compromised Cisco routers for network communications.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) compromised Ubiquiti network devices to act as collection devices for credentials compromised via phishing webpages.(Citation: Leonard TAG 2023) [Leonard TAG 2023](https://blog.google/threat-analysis-group/ukraine-remains-russias-biggest-cyber-focus-in-2023/)
- [C0029 - Cutting Edge](../../../../Threat%20Intelligence/Campaigns/C0029%20-%20Cutting%20Edge.md) — During [Cutting Edge](https://attack.mitre.org/campaigns/C0029), threat actors used compromised and out-of-support Cyberoam VPN appliances for C2.(Citation: Mandiant Cutting Edge January 2024)(Citation: Volexity Ivanti Global Exploitation January 2024) [Volexity Ivanti Global Exploitation January 2024](https://www.volexity.com/blog/2024/01/15/ivanti-connect-secure-vpn-exploitation-goes-global/) · [Mandiant Cutting Edge January 2024](https://www.mandiant.com/resources/blog/suspected-apt-targets-ivanti-zero-day)
- [C0053 - FLORAHOX Activity](../../../../Threat%20Intelligence/Campaigns/C0053%20-%20FLORAHOX%20Activity.md) — [FLORAHOX Activity](https://attack.mitre.org/campaigns/C0053) has compromised network routers and IoT devices for the ORB network.(Citation: ORB Mandiant) [ORB Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-orb-networks)
- [C0035 - KV Botnet Activity](../../../../Threat%20Intelligence/Campaigns/C0035%20-%20KV%20Botnet%20Activity.md) — [KV Botnet Activity](https://attack.mitre.org/campaigns/C0035) focuses on compromise of small office-home office (SOHO) network devices to build the subsequent botnet.(Citation: Lumen KVBotnet 2023) [Lumen KVBotnet 2023](https://blog.lumen.com/routers-roasting-on-an-open-firewall-the-kv-botnet-investigation/)
- [G0065 - Leviathan](../../../../Threat%20Intelligence/Groups/G0065%20-%20Leviathan.md) — [Leviathan](https://attack.mitre.org/groups/G0065) has used compromised networking devices, such as small office/home office (SOHO) devices, as operational command and control infrastructure.(Citation: CISA Leviathan 2024) [CISA Leviathan 2024](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-190a)
- [C0055 - Quad7 Activity](../../../../Threat%20Intelligence/Campaigns/C0055%20-%20Quad7%20Activity.md) — [Quad7 Activity](https://attack.mitre.org/campaigns/C0055) has compromised network devices, such as IP cameras, Network Attached Storage (NAS) devices, and SOHO routers, to leverage for follow-on activity.(Citation: Microsoft Storm-0940)(Citation: Sekoia 7777 Botnet JUL 2024) [Sekoia 7777 Botnet JUL 2024](https://blog.sekoia.io/solving-the-7777-botnet-enigma-a-cybersecurity-quest/) · [Microsoft Storm-0940](https://www.microsoft.com/en-us/security/blog/2024/10/31/chinese-threat-actor-storm-0940-uses-credentials-from-password-spray-attacks-from-a-covert-network/)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has leveraged compromised routers to facilitate operations.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)
- [C0039 - Versa Director Zero Day Exploitation](../../../../Threat%20Intelligence/Campaigns/C0039%20-%20Versa%20Director%20Zero%20Day%20Exploitation.md) — [Versa Director Zero Day Exploitation](https://attack.mitre.org/campaigns/C0039) used compromised small office/home office (SOHO) devices to interact with vulnerable Versa Director servers.(Citation: Lumen Versa 2024) [Lumen Versa 2024](https://www.lumen.com/blog/en-us/uncovering-versa-director-zero-day-exploitation)
- [G1017 - Volt Typhoon](../../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has compromised small office and home office (SOHO) network edge devices, many of which were located in the same geographic area as the victim, to proxy network traffic.(Citation: Microsoft Volt Typhoon May 2023)(Citation: Joint Cybersecurity Advisory Volt Typhoon June 2023) [Microsoft Volt Typhoon May 2023](https://www.microsoft.com/en-us/security/blog/2023/05/24/volt-typhoon-targets-us-critical-infrastructure-with-living-off-the-land-techniques/) · [Joint Cybersecurity Advisory Volt Typhoon June 2023](https://media.defense.gov/2023/May/24/2003229517/-1/-1/0/CSA_Living_off_the_Land.PDF)
- [G0128 - ZIRCONIUM](../../../../Threat%20Intelligence/Groups/G0128%20-%20ZIRCONIUM.md) — [ZIRCONIUM](https://attack.mitre.org/groups/G0128) has compromised network devices such as small office and home office (SOHO) routers and IoT devices for ORB (operational relay box) [Proxy](https://attack.mitre.org/techniques/T1090) networks.(Citation: ORB APT31)(Citation: ORB Mandiant) [ORB APT31](https://therecord.media/chinese-hacking-group-apt31-uses-mesh-of-home-routers-to-disguise-attacks) · [ORB Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-orb-networks)

## Detection strategies

- [DET0859 - Detection of Network Devices](../../../../Defenses/Detection%20Strategies/DET0859%20-%20Detection%20of%20Network%20Devices.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [Wired Russia Cyberwar](https://www.wired.com/story/russia-ukraine-cyberattacks-mandiant/)
- [Mandiant Fortinet Zero Day](https://www.mandiant.com/resources/blog/fortinet-malware-ecosystem)
- [Justice GRU 2024](https://www.justice.gov/opa/pr/justice-department-conducts-court-authorized-disruption-botnet-controlled-russian)
