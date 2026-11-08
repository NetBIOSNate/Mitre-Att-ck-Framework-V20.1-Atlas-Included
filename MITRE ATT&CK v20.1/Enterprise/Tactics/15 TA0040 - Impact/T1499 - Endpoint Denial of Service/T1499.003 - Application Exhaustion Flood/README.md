# T1499.003 - Application Exhaustion Flood

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1499 - Endpoint Denial of Service](../README.md)

Adversaries may target resource intensive features of applications to cause a denial of service (DoS), denying availability to those applications. For example, specific features in web applications may be highly resource intensive. Repeated requests to those features may be able to exhaust system resources and deny access to the application or the server itself.(Citation: Arbor AnnualDoSreport Jan 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1499/003)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [IaaS](../../../../Platforms/IaaS.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Leverage services provided by Content Delivery Networks (CDN) or providers specializing in DoS mitigations to filter traffic upstream from services.(Citation: CERT-EU DDoS March 2017) Filter boundary traffic by blocking source addresses sourcing the attack, blocking ports that are being targeted, or blocking protocols being used for transport. [CERT-EU DDoS March 2017](http://cert.europa.eu/static/WhitePapers/CERT-EU_Security_Whitepaper_DDoS_17-003.pdf)

## Detection strategies

- [DET0415 - Application Exhaustion Flood Detection Across Platforms](../../../../Defenses/Detection%20Strategies/DET0415%20-%20Application%20Exhaustion%20Flood%20Detection%20Across%20Platforms.md)

## Sources

- [Cisco DoSdetectNetflow](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/netflow/configuration/15-mt/nf-15-mt-book/nf-detct-analy-thrts.pdf)
- [Arbor AnnualDoSreport Jan 2018](https://pages.arbornetworks.com/rs/082-KNA-087/images/13th_Worldwide_Infrastructure_Security_Report.pdf)
