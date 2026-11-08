# T1464 - Network Denial of Service

[Mobile](../../../README.md) / [Impact](../README.md)

Adversaries may perform Network Denial of Service (DoS) attacks to degrade or block the availability of targeted resources to users. Network DoS can be performed by exhausting the network bandwidth that services rely on, or by jamming the signal going to or coming from devices. 

A Network DoS will occur when an adversary is able to jam radio signals (e.g. Wi-Fi, cellular, GPS) around a device to prevent it from communicating. For example, to jam cellular signal, an adversary may use a handheld signal jammer, which jam devices within the jammer’s operational range.(Citation: NIST-SP800187) 

Usage of cellular jamming has been documented in several arrests reported in the news.(Citation: CNET-Celljammer)(Citation: NYTimes-Celljam)(Citation: Digitaltrends-Celljam)(Citation: Arstechnica-Celljam)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1464)

**Tactics**  [Impact](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Detection strategies

- [DET0639 - Detection of Network Denial of Service](../../../Defenses/Detection%20Strategies/DET0639%20-%20Detection%20of%20Network%20Denial%20of%20Service.md)

## Procedure examples

- [S1062 - S.O.V.A.](../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) has C2 commands to add an infected device to a DDoS pool.(Citation: threatfabric_sova_0921) [threatfabric_sova_0921](https://www.threatfabric.com/blogs/sova-new-trojan-with-fowl-intentions.html)

## Sources

- [CNET-Celljammer](https://www.cnet.com/news/man-put-cell-phone-jammer-in-car-to-stop-driver-calls-fcc-says/)
- [Arstechnica-Celljam](https://arstechnica.com/tech-policy/2016/03/man-accused-of-jamming-passengers-cell-phones-on-chicago-subway/)
- [NIST-SP800187](http://csrc.nist.gov/publications/drafts/800-187/sp800_187_draft.pdf)
- [NYTimes-Celljam](https://www.nytimes.com/2007/11/04/technology/04jammer.html)
- [Digitaltrends-Celljam](https://www.digitaltrends.com/mobile/florida-teacher-punished-after-signal-jamming-his-students-cell-phones/)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-7.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-8.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/lan-pan-threats/LPN-5.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/gps-threats/GPS-0.html)
