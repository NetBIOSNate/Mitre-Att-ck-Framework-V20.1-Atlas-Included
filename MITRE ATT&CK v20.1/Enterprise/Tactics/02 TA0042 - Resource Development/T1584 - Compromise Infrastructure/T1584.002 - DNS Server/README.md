# T1584.002 - DNS Server

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1584 - Compromise Infrastructure](../README.md)

Adversaries may compromise third-party DNS servers that can be used during targeting. During post-compromise activity, adversaries may utilize DNS traffic for various tasks, including for Command and Control (ex: [Application Layer Protocol](https://attack.mitre.org/techniques/T1071)). Instead of setting up their own DNS servers, adversaries may compromise third-party DNS servers in support of operations.

By compromising DNS servers, adversaries can alter DNS records. Such control can allow for redirection of an organization's traffic, facilitating Collection and Credential Access efforts for the adversary.(Citation: Talos DNSpionage Nov 2018)(Citation: FireEye DNS Hijack 2019)  Additionally, adversaries may leverage such control in conjunction with [Digital Certificates](https://attack.mitre.org/techniques/T1588/004) to redirect traffic to adversary-controlled infrastructure, mimicking normal trusted network communications.(Citation: FireEye DNS Hijack 2019)(Citation: Crowdstrike DNS Hijack 2019) Alternatively, they may be able to prove ownership of a domain to a SaaS service in order to assert control of the service or create a new administrative [Cloud Account](https://attack.mitre.org/techniques/T1136/003).(Citation: CyberCX SaaS Domain Hijacking 2025) Adversaries may also be able to silently create subdomains pointed at malicious servers without tipping off the actual owner of the DNS server.(Citation: CiscoAngler)(Citation: Proofpoint Domain Shadowing)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1584/002)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has reconfigured a victim's DNS records to actor-controlled domains and websites.(Citation: NCC Group LAPSUS Apr 2022) [NCC Group LAPSUS Apr 2022](https://www.nccgroup.com/research-blog/lapsus-recent-techniques-tactics-and-procedures/)
- [G1041 - Sea Turtle](../../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) modified Name Server (NS) items to refer to [Sea Turtle](https://attack.mitre.org/groups/G1041)-controlled DNS servers to provide responses for all DNS lookups.(Citation: Talos Sea Turtle 2019)(Citation: Talos Sea Turtle 2019_2) [Talos Sea Turtle 2019](https://blog.talosintelligence.com/seaturtle/) · [Talos Sea Turtle 2019_2](https://blog.talosintelligence.com/sea-turtle-keeps-on-swimming/)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0891 - Detection of DNS Server](../../../../Defenses/Detection%20Strategies/DET0891%20-%20Detection%20of%20DNS%20Server.md)

## Sources

- [FireEye DNS Hijack 2019](https://www.fireeye.com/blog/threat-research/2019/01/global-dns-hijacking-campaign-dns-record-manipulation-at-scale.html)
- [Crowdstrike DNS Hijack 2019](https://www.crowdstrike.com/blog/widespread-dns-hijacking-activity-targets-multiple-sectors/)
- [Talos DNSpionage Nov 2018](https://blog.talosintelligence.com/2018/11/dnspionage-campaign-targets-middle-east.html)
- [CiscoAngler](https://blogs.cisco.com/security/talos/angler-domain-shadowing)
- [Proofpoint Domain Shadowing](https://www.proofpoint.com/us/threat-insight/post/The-Shadow-Knows)
- [CyberCX SaaS Domain Hijacking 2025](https://cybercx.com.au/blog/keys-to-the-saas-kingdom/)
