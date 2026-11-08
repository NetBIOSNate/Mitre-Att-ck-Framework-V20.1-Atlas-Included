# T1583 - Acquire Infrastructure

[Enterprise](../../../README.md) / [Resource Development](../README.md)

Adversaries may buy, lease, rent, or obtain infrastructure that can be used during targeting. A wide variety of infrastructure exists for hosting and orchestrating adversary operations. Infrastructure solutions include physical or cloud servers, domains, and third-party web services.(Citation: TrendmicroHideoutsLease) Some infrastructure providers offer free trial periods, enabling infrastructure acquisition at limited to no cost.(Citation: Free Trial PurpleUrchin) Additionally, botnets are available for rent or purchase.

Use of these infrastructure solutions allows adversaries to stage, launch, and execute operations. Solutions may help adversary operations blend in with traffic that is seen as normal, such as contacting third-party web services or acquiring infrastructure to support [Proxy](https://attack.mitre.org/techniques/T1090), including from residential proxy services.(Citation: amnesty_nso_pegasus)(Citation: FBI Proxies Credential Stuffing)(Citation: Mandiant APT29 Microsoft 365 2022) Depending on the implementation, adversaries may use infrastructure that makes it difficult to physically tie back to them as well as utilize infrastructure that can be rapidly provisioned, modified, and shut down.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1583)

**Tactics**  [Resource Development](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1583.005 - Botnet](T1583.005%20-%20Botnet/README.md)
- [T1583.002 - DNS Server](T1583.002%20-%20DNS%20Server/README.md)
- [T1583.001 - Domains](T1583.001%20-%20Domains/README.md)
- [T1583.008 - Malvertising](T1583.008%20-%20Malvertising/README.md)
- [T1583.004 - Server](T1583.004%20-%20Server/README.md)
- [T1583.007 - Serverless](T1583.007%20-%20Serverless/README.md)
- [T1583.003 - Virtual Private Server](T1583.003%20-%20Virtual%20Private%20Server/README.md)
- [T1583.006 - Web Services](T1583.006%20-%20Web%20Services/README.md)

## Procedure examples

- [G1030 - Agrius](../../../Threat%20Intelligence/Groups/G1030%20-%20Agrius.md) — [Agrius](https://attack.mitre.org/groups/G1030) typically uses commercial VPN services for anonymizing last-hop traffic to victim networks, such as ProtonVPN.(Citation: SentinelOne Agrius 2021) [SentinelOne Agrius 2021](https://assets.sentinelone.com/sentinellabs/evol-agrius)
- [G1052 - Contagious Interview](../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has used services such as Astrill VPN.(Citation: Sentinel One Contagious Interview ClickFix September 2025)(Citation: Recorded Future Contagious Inteview BeaverTail InvisibleFerret OtterCookie February 2025) [Sentinel One Contagious Interview ClickFix September 2025](https://www.sentinelone.com/labs/contagious-interview-threat-actors-scout-cyber-intel-platforms-reveal-plans-and-ops/) · [Recorded Future Contagious Inteview BeaverTail InvisibleFerret OtterCookie February 2025](https://www.recordedfuture.com/research/inside-the-scam-north-koreas-it-worker-threat)
- [G1003 - Ember Bear](../../../Threat%20Intelligence/Groups/G1003%20-%20Ember%20Bear.md) — [Ember Bear](https://attack.mitre.org/groups/G1003) uses services such as IVPN, SurfShark, and Tor to add anonymization to operations.(Citation: Cadet Blizzard emerges as novel threat actor) [Cadet Blizzard emerges as novel threat actor](https://www.microsoft.com/en-us/security/blog/2023/06/14/cadet-blizzard-emerges-as-a-novel-and-distinct-russian-threat-actor/)
- [G0119 - Indrik Spider](../../../Threat%20Intelligence/Groups/G0119%20-%20Indrik%20Spider.md) — [Indrik Spider](https://attack.mitre.org/groups/G0119) has purchased access to victim VPNs to facilitate access to victim environments.(Citation: Mandiant_UNC2165) [Mandiant_UNC2165](https://cloud.google.com/blog/topics/threat-intelligence/unc2165-shifts-to-evade-sanctions/)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used funds from stolen and laundered cryptocurrency to acquire operational infrastructure.(Citation: Mandiant APT43 March 2024) [Mandiant APT43 March 2024](https://services.google.com/fh/files/misc/apt43-report-en.pdf)
- [G0034 - Sandworm Team](../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) used various third-party email campaign management services to deliver phishing emails.(Citation: Leonard TAG 2023) [Leonard TAG 2023](https://blog.google/threat-analysis-group/ukraine-remains-russias-biggest-cyber-focus-in-2023/)
- [G1041 - Sea Turtle](../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) accessed victim networks from VPN service provider networks.(Citation: Hunt Sea Turtle 2024) [Hunt Sea Turtle 2024](https://www.huntandhackett.com/blog/turkish-espionage-campaigns)
- [G1033 - Star Blizzard](../../../Threat%20Intelligence/Groups/G1033%20-%20Star%20Blizzard.md) — [Star Blizzard](https://attack.mitre.org/groups/G1033) has used HubSpot and MailerLite marketing platform services to hide the true sender of phishing emails.(Citation: StarBlizzard) [StarBlizzard](https://www.microsoft.com/en-us/security/blog/2023/12/07/star-blizzard-increases-sophistication-and-evasion-in-ongoing-attacks/)
- [G1056 - TeamPCP](../../../Threat%20Intelligence/Groups/G1056%20-%20TeamPCP.md) — In May 2026 [TeamPCP](https://attack.mitre.org/groups/G1056) announced co-ownership of the BreachForums cybercriminal forum claiming responsibility for platform operations, dispute resolution, personnel vetting, and hosting monetary contests.(Citation: Flashpoint Mini Shai-Hulud MAY 2026) [Flashpoint Mini Shai-Hulud MAY 2026](https://flashpoint.io/blog/mini-shai-hulud-worm-new-era-ci-cd-exploitation/)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0895 - Detection of Acquire Infrastructure](../../../Defenses/Detection%20Strategies/DET0895%20-%20Detection%20of%20Acquire%20Infrastructure.md)

## Sources

- [amnesty_nso_pegasus](https://www.amnesty.org/en/latest/research/2021/07/forensic-methodology-report-how-to-catch-nso-groups-pegasus/)
- [Mandiant APT29 Microsoft 365 2022](https://www.mandiant.com/resources/blog/apt29-continues-targeting-microsoft)
- [FBI Proxies Credential Stuffing](https://www.ic3.gov/Media/News/2022/220818.pdf)
- [Free Trial PurpleUrchin](https://unit42.paloaltonetworks.com/purpleurchin-steals-cloud-resources/)
- [Koczwara Beacon Hunting Sep 2021](https://michaelkoczwara.medium.com/cobalt-strike-c2-hunting-with-shodan-c448d501a6e2)
- [TrendmicroHideoutsLease](https://documents.trendmicro.com/assets/wp/wp-criminal-hideouts-for-lease.pdf)
- [Mandiant SCANdalous Jul 2020](https://cloud.google.com/blog/topics/threat-intelligence/scandalous-external-detection-using-network-scan-data-and-automation/)
- [ThreatConnect Infrastructure Dec 2020](https://web.archive.org/web/20221130114004/https://threatconnect.com/blog/infrastructure-research-hunting/)
