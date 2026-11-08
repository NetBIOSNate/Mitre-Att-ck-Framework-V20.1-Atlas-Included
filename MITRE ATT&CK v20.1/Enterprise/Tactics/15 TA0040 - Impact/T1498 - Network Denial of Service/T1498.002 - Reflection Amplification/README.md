# T1498.002 - Reflection Amplification

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1498 - Network Denial of Service](../README.md)

Adversaries may attempt to cause a denial of service (DoS) by reflecting a high-volume of network traffic to a target. This type of Network DoS takes advantage of a third-party server intermediary that hosts and will respond to a given spoofed source IP address. This third-party server is commonly termed a reflector. An adversary accomplishes a reflection attack by sending packets to reflectors with the spoofed address of the victim. Similar to Direct Network Floods, more than one system may be used to conduct the attack, or a botnet may be used. Likewise, one or more reflectors may be used to focus traffic on the target.(Citation: Cloudflare ReflectionDoS May 2017) This Network DoS attack may also reduce the availability and functionality of the targeted system(s) and network.

Reflection attacks often take advantage of protocols with larger responses than requests in order to amplify their traffic, commonly known as a Reflection Amplification attack. Adversaries may be able to generate an increase in volume of attack traffic that is several orders of magnitude greater than the requests sent to the amplifiers. The extent of this increase will depend upon many variables, such as the protocol in question, the technique used, and the amplifying servers that actually produce the amplification in attack volume. Two prominent protocols that have enabled Reflection Amplification Floods are DNS(Citation: Cloudflare DNSamplficationDoS) and NTP(Citation: Cloudflare NTPamplifciationDoS), though the use of several others in the wild has been documented.(Citation: Arbor AnnualDoSreport Jan 2018)  In particular, the memcache protocol showed itself to be a powerful protocol, with amplification sizes up to 51,200 times the requesting packet.(Citation: Cloudflare Memcrashed Feb 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1498/002)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [IaaS](../../../../Platforms/IaaS.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — When flood volumes exceed the capacity of the network connection being targeted, it is typically necessary to intercept the incoming traffic upstream to filter out the attack traffic from the legitimate traffic. Such defenses can be provided by the hosting Internet Service Provider (ISP) or by a 3rd party such as a Content Delivery Network (CDN) or providers specializing in DoS mitigations.(Citation: CERT-EU DDoS March 2017) Depending on flood volume, on-premises filtering may be possible by blocking source addresses sourcing the attack, blocking ports that are being targeted, or blocking protocols being used for transport.(Citation: CERT-EU DDoS March 2017) As immediate response may require rapid engagement of 3rd parties, analyze the risk associated to critical resources being affected by Network DoS attacks and create a disaster recovery plan/business continuity plan to respond to incidents.(Citation: CERT-EU DDoS March 2017) [CERT-EU DDoS March 2017](http://cert.europa.eu/static/WhitePapers/CERT-EU_Security_Whitepaper_DDoS_17-003.pdf)

## Detection strategies

- [DET0408 - Detection Strategy for Reflection Amplification DoS (T1498.002)](../../../../Defenses/Detection%20Strategies/DET0408%20-%20Detection%20Strategy%20for%20Reflection%20Amplification%20DoS%20%28T1498.002%29.md)

## Sources

- [Cloudflare DNSamplficationDoS](https://www.cloudflare.com/learning/ddos/dns-amplification-ddos-attack/)
- [Cloudflare NTPamplifciationDoS](https://www.cloudflare.com/learning/ddos/ntp-amplification-ddos-attack/)
- [Cloudflare ReflectionDoS May 2017](https://blog.cloudflare.com/reflections-on-reflections/)
- [Cloudflare Memcrashed Feb 2018](https://blog.cloudflare.com/memcrashed-major-amplification-attacks-from-port-11211/)
- [Arbor AnnualDoSreport Jan 2018](https://pages.arbornetworks.com/rs/082-KNA-087/images/13th_Worldwide_Infrastructure_Security_Report.pdf)
