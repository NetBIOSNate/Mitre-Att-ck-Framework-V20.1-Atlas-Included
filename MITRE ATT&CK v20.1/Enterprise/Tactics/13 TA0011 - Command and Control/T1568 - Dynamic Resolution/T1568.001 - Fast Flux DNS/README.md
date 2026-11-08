# T1568.001 - Fast Flux DNS

[Enterprise](../../../../README.md) / [Command and Control](../../README.md) / [T1568 - Dynamic Resolution](../README.md)

Adversaries may use Fast Flux DNS to hide a command and control channel behind an array of rapidly changing IP addresses linked to a single domain resolution. This technique uses a fully qualified domain name, with multiple IP addresses assigned to it which are swapped with high frequency, using a combination of round robin IP addressing and short Time-To-Live (TTL) for a DNS resource record.(Citation: MehtaFastFluxPt1)(Citation: MehtaFastFluxPt2)(Citation: Fast Flux - Welivesecurity)

The simplest, "single-flux" method, involves registering and de-registering an address as part of the DNS A (address) record list for a single DNS name. These registrations have a five-minute average lifespan, resulting in a constant shuffle of IP address resolution.(Citation: Fast Flux - Welivesecurity)

In contrast, the "double-flux" method registers and de-registers an address as part of the DNS Name Server record list for the DNS zone, providing additional resilience for the connection. With double-flux additional hosts can act as a proxy to the C2 host, further insulating the true source of the C2 channel.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1568/001)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md), [ESXi](../../../../Platforms/ESXi.md)

## Detection strategies

- [DET0485 - Detection Strategy for Dynamic Resolution using Fast Flux DNS](../../../../Defenses/Detection%20Strategies/DET0485%20-%20Detection%20Strategy%20for%20Dynamic%20Resolution%20using%20Fast%20Flux%20DNS.md)

## Procedure examples

- [S1025 - Amadey](../../../../Threat%20Intelligence/Software/Malware/S1025%20-%20Amadey.md) — [Amadey](https://attack.mitre.org/software/S1025) has used fast flux DNS for its C2.(Citation: Korean FSI TA505 2020) [Korean FSI TA505 2020](https://www.fsec.or.kr/user/bbs/fsec/163/344/bbsDataView/1382.do?page=1&column=&search=&searchSDate=&searchEDate=&bbsDataCategory=)
- [G0047 - Gamaredon Group](../../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has used fast flux DNS to mask their command and control channel behind rotating IP addresses.(Citation: unit42_gamaredon_dec2022)(Citation: ESET Gamaredon Sept2024)(Citation: SilentPush_GamaredonFastFlux_Sept2023) Additionally, [Gamaredon Group](https://attack.mitre.org/groups/G0047) has used a low-frequency variant of the single-flux method.(Citation: Huntio_GamaredonFlux_Apr2025) [Huntio_GamaredonFlux_Apr2025](https://hunt.io/blog/state-sponsored-activity-gamaredon-shadowpad) · [ESET Gamaredon Sept2024](https://web-assets.esetstatic.com/wls/en/papers/white-papers/cyberespionage-gamaredon-way.pdf) · [SilentPush_GamaredonFastFlux_Sept2023](https://www.silentpush.com/blog/from-russia-with-a-71/) · [unit42_gamaredon_dec2022](https://unit42.paloaltonetworks.com/trident-ursa/)
- [S0032 - gh0st RAT](../../../../Threat%20Intelligence/Software/Malware/S0032%20-%20gh0st%20RAT.md) — [gh0st RAT](https://attack.mitre.org/software/S0032) operators have used dynamic DNS to mask the true location of their C2 behind rapidly changing IP addresses.(Citation: Gh0stRAT ATT March 2019) [Gh0stRAT ATT March 2019](https://cybersecurity.att.com/blogs/labs-research/the-odd-case-of-a-gh0strat-variant)
- [G0045 - menuPass](../../../../Threat%20Intelligence/Groups/G0045%20-%20menuPass.md) — [menuPass](https://attack.mitre.org/groups/G0045) has used dynamic DNS service providers to host malicious domains.(Citation: District Court of NY APT10 Indictment December 2018) [District Court of NY APT10 Indictment December 2018](https://www.justice.gov/opa/page/file/1122671/download)
- [S0385 - njRAT](../../../../Threat%20Intelligence/Software/Malware/S0385%20-%20njRAT.md) — [njRAT](https://attack.mitre.org/software/S0385) has used a fast flux DNS for C2 IP resolution.(Citation: Trend Micro njRAT 2018) [Trend Micro njRAT 2018](https://blog.trendmicro.com/trendlabs-security-intelligence/autoit-compiled-worm-affecting-removable-media-delivers-fileless-version-of-bladabindi-njrat-backdoor/)
- [G0092 - TA505](../../../../Threat%20Intelligence/Groups/G0092%20-%20TA505.md) — [TA505](https://attack.mitre.org/groups/G0092) has used fast flux to mask botnets by distributing payloads across multiple IPs.(Citation: Trend Micro TA505 June 2019) [Trend Micro TA505 June 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/shifting-tactics-breaking-down-ta505-groups-use-of-html-rats-and-other-techniques-in-latest-campaigns/)

## Sources

- [Fast Flux - Welivesecurity](https://www.welivesecurity.com/2017/01/12/fast-flux-networks-work/)
- [MehtaFastFluxPt1](https://resources.infosecinstitute.com/fast-flux-networks-working-detection-part-1/#gref)
- [MehtaFastFluxPt2](https://resources.infosecinstitute.com/fast-flux-networks-working-detection-part-2/#gref)
