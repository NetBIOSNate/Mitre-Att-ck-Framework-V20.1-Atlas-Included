# T1583.002 - DNS Server

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1583 - Acquire Infrastructure](../README.md)

Adversaries may set up their own Domain Name System (DNS) servers that can be used during targeting. During post-compromise activity, adversaries may utilize DNS traffic for various tasks, including for Command and Control (ex: [Application Layer Protocol](https://attack.mitre.org/techniques/T1071)). Instead of hijacking existing DNS servers, adversaries may opt to configure and run their own DNS servers in support of operations.

By running their own DNS servers, adversaries can have more control over how they administer server-side DNS C2 traffic ([DNS](https://attack.mitre.org/techniques/T1071/004)). With control over a DNS server, adversaries can configure DNS applications to provide conditional responses to malware and, generally, have more flexibility in the structure of the DNS-based C2 channel.(Citation: Unit42 DNS Mar 2019)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1583/002)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Procedure examples

- [G0001 - Axiom](../../../../Threat%20Intelligence/Groups/G0001%20-%20Axiom.md) — [Axiom](https://attack.mitre.org/groups/G0001) has acquired dynamic DNS services for use in the targeting of intended victims.(Citation: Novetta-Axiom) [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)
- [G1001 - HEXANE](../../../../Threat%20Intelligence/Groups/G1001%20-%20HEXANE.md) — [HEXANE](https://attack.mitre.org/groups/G1001) has set up custom DNS servers to send commands to compromised hosts via TXT records.(Citation: Zscaler Lyceum DnsSystem June 2022) [Zscaler Lyceum DnsSystem June 2022](https://www.zscaler.com/blogs/security-research/lyceum-net-dns-backdoor)
- [G1041 - Sea Turtle](../../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) built adversary-in-the-middle DNS servers to impersonate legitimate services that were later used to capture credentials.(Citation: Talos Sea Turtle 2019_2)(Citation: Talos Sea Turtle 2019) [Talos Sea Turtle 2019](https://blog.talosintelligence.com/seaturtle/) · [Talos Sea Turtle 2019_2](https://blog.talosintelligence.com/sea-turtle-keeps-on-swimming/)

## Detection strategies

- [DET0862 - Detection of DNS Server](../../../../Defenses/Detection%20Strategies/DET0862%20-%20Detection%20of%20DNS%20Server.md)

## Sources

- [Unit42 DNS Mar 2019](https://unit42.paloaltonetworks.com/dns-tunneling-how-dns-can-be-abused-by-malicious-actors/)
