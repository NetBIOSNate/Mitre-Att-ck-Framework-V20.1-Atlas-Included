# T1584 - Compromise Infrastructure

[Enterprise](../../../README.md) / [Resource Development](../README.md)

Adversaries may compromise third-party infrastructure that can be used during targeting. Infrastructure solutions include physical or cloud servers, domains, network devices, and third-party web and DNS services. Instead of buying, leasing, or renting infrastructure an adversary may compromise infrastructure and use it during other phases of the adversary lifecycle.(Citation: Mandiant APT1)(Citation: ICANNDomainNameHijacking)(Citation: Talos DNSpionage Nov 2018)(Citation: FireEye EPS Awakens Part 2) Additionally, adversaries may compromise numerous machines to form a botnet they can leverage.

Use of compromised infrastructure allows adversaries to stage, launch, and execute operations. Compromised infrastructure can help adversary operations blend in with traffic that is seen as normal, such as contact with high reputation or trusted sites. For example, adversaries may leverage compromised infrastructure (potentially also in conjunction with [Digital Certificates](https://attack.mitre.org/techniques/T1588/004)) to further blend in and support staged information gathering and/or [Phishing](https://attack.mitre.org/techniques/T1566) campaigns.(Citation: FireEye DNS Hijack 2019) Adversaries may also compromise numerous machines to support [Proxy](https://attack.mitre.org/techniques/T1090) and/or proxyware services or to form a botnet.(Citation: amnesty_nso_pegasus)(Citation: Sysdig Proxyjacking) Additionally, adversaries may compromise infrastructure residing in close proximity to a target in order to gain [Initial Access](https://attack.mitre.org/tactics/TA0001) via [Wi-Fi Networks](https://attack.mitre.org/techniques/T1669).(Citation: Nearest Neighbor Volexity)

By using compromised infrastructure, adversaries may enable follow-on malicious operations. Prior to targeting, adversaries may also compromise the infrastructure of other adversaries.(Citation: NSA NCSC Turla OilRig)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1584)

**Tactics**  [Resource Development](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1584.005 - Botnet](T1584.005%20-%20Botnet/README.md)
- [T1584.002 - DNS Server](T1584.002%20-%20DNS%20Server/README.md)
- [T1584.001 - Domains](T1584.001%20-%20Domains/README.md)
- [T1584.008 - Network Devices](T1584.008%20-%20Network%20Devices/README.md)
- [T1584.004 - Server](T1584.004%20-%20Server/README.md)
- [T1584.007 - Serverless](T1584.007%20-%20Serverless/README.md)
- [T1584.003 - Virtual Private Server](T1584.003%20-%20Virtual%20Private%20Server/README.md)
- [T1584.006 - Web Services](T1584.006%20-%20Web%20Services/README.md)

## Procedure examples

- [C0051 - APT28 Nearest Neighbor Campaign](../../../Threat%20Intelligence/Campaigns/C0051%20-%20APT28%20Nearest%20Neighbor%20Campaign.md) — During [APT28 Nearest Neighbor Campaign](https://attack.mitre.org/campaigns/C0051), [APT28](https://attack.mitre.org/groups/G0007) compromised third-party infrastructure in physical proximity to targets of interest for follow-on activities.(Citation: Nearest Neighbor Volexity) [Nearest Neighbor Volexity](https://www.volexity.com/blog/2024/11/22/the-nearest-neighbor-attack-how-a-russian-apt-weaponized-nearby-wi-fi-networks-for-covert-access/)
- [C0043 - Indian Critical Infrastructure Intrusions](../../../Threat%20Intelligence/Campaigns/C0043%20-%20Indian%20Critical%20Infrastructure%20Intrusions.md) — [Indian Critical Infrastructure Intrusions](https://attack.mitre.org/campaigns/C0043) included the use of compromised infrastructure, such as DVR and IP camera devices, for command and control purposes in [ShadowPad](https://attack.mitre.org/software/S0596) activity.(Citation: RecordedFuture RedEcho 2022) [RecordedFuture RedEcho 2022](https://go.recordedfuture.com/hubfs/reports/ta-2022-0406.pdf)

## Detection strategies

- [DET0885 - Detection of Compromise Infrastructure](../../../Defenses/Detection%20Strategies/DET0885%20-%20Detection%20of%20Compromise%20Infrastructure.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [amnesty_nso_pegasus](https://www.amnesty.org/en/latest/research/2021/07/forensic-methodology-report-how-to-catch-nso-groups-pegasus/)
- [Sysdig Proxyjacking](https://sysdig.com/blog/proxyjacking-attackers-log4j-exploited/)
- [FireEye DNS Hijack 2019](https://www.fireeye.com/blog/threat-research/2019/01/global-dns-hijacking-campaign-dns-record-manipulation-at-scale.html)
- [ICANNDomainNameHijacking](https://www.icann.org/en/ssac/registration-services/documents/sac-007-domain-name-hijacking-incidents-threats-risks-and-remediation-12-07-2005-en)
- [Koczwara Beacon Hunting Sep 2021](https://michaelkoczwara.medium.com/cobalt-strike-c2-hunting-with-shodan-c448d501a6e2)
- [Nearest Neighbor Volexity](https://www.volexity.com/blog/2024/11/22/the-nearest-neighbor-attack-how-a-russian-apt-weaponized-nearby-wi-fi-networks-for-covert-access/)
- [Mandiant APT1](https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf)
- [Talos DNSpionage Nov 2018](https://blog.talosintelligence.com/2018/11/dnspionage-campaign-targets-middle-east.html)
- [NSA NCSC Turla OilRig](https://media.defense.gov/2019/Oct/18/2002197242/-1/-1/0/NSA_CSA_Turla_20191021%20ver%204%20-%20nsa.gov.pdf)
- [Mandiant SCANdalous Jul 2020](https://cloud.google.com/blog/topics/threat-intelligence/scandalous-external-detection-using-network-scan-data-and-automation/)
- [ThreatConnect Infrastructure Dec 2020](https://web.archive.org/web/20221130114004/https://threatconnect.com/blog/infrastructure-research-hunting/)
- [FireEye EPS Awakens Part 2](https://web.archive.org/web/20151226205946/https://www.fireeye.com/blog/threat-research/2015/12/the-eps-awakens-part-two.html)
