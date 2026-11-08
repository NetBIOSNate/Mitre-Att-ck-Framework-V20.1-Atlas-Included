# T1499.002 - Service Exhaustion Flood

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1499 - Endpoint Denial of Service](../README.md)

Adversaries may target the different network services provided by systems to conduct a denial of service (DoS). Adversaries often target the availability of DNS and web services; however, others have been targeted as well.(Citation: Arbor AnnualDoSreport Jan 2018) Web server software can be attacked through a variety of means, some of which apply generally while others are specific to the software being used to provide the service.

One example of this type of attack is known as a simple HTTP flood, where an adversary sends a large number of HTTP requests to a web server to overwhelm it and/or an application that runs on top of it. This flood relies on raw volume to accomplish the objective, exhausting any of the various resources required by the victim software to provide the service.(Citation: Cloudflare HTTPflood)

Another variation, known as an SSL renegotiation attack, takes advantage of a protocol feature in SSL/TLS. The SSL/TLS protocol suite includes mechanisms for the client and server to agree on an encryption algorithm to use for subsequent secure connections. If SSL renegotiation is enabled, a request can be made for renegotiation of the crypto algorithm. In a renegotiation attack, the adversary establishes an SSL/TLS connection and then proceeds to make a series of renegotiation requests. Because the cryptographic renegotiation has a meaningful cost in computation cycles, this can cause an impact to the availability of the service when done in volume.(Citation: Arbor SSLDoS April 2012)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1499/002)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [IaaS](../../../../Platforms/IaaS.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0173 - Detection Strategy for Endpoint DoS via Service Exhaustion Flood](../../../../Defenses/Detection%20Strategies/DET0173%20-%20Detection%20Strategy%20for%20Endpoint%20DoS%20via%20Service%20Exhaustion%20Flood.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Leverage services provided by Content Delivery Networks (CDN) or providers specializing in DoS mitigations to filter traffic upstream from services.(Citation: CERT-EU DDoS March 2017) Filter boundary traffic by blocking source addresses sourcing the attack, blocking ports that are being targeted, or blocking protocols being used for transport. [CERT-EU DDoS March 2017](http://cert.europa.eu/static/WhitePapers/CERT-EU_Security_Whitepaper_DDoS_17-003.pdf)

## Sources

- [Arbor SSLDoS April 2012](https://www.netscout.com/blog/asert/ddos-attacks-ssl-something-old-something-new)
- [Cloudflare HTTPflood](https://www.cloudflare.com/learning/ddos/http-flood-ddos-attack/)
- [Arbor AnnualDoSreport Jan 2018](https://pages.arbornetworks.com/rs/082-KNA-087/images/13th_Worldwide_Infrastructure_Security_Report.pdf)
