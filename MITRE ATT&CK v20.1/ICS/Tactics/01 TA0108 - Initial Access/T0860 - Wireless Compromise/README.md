# T0860 - Wireless Compromise

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may perform wireless compromise as a method of gaining communications and unauthorized access to a wireless network. Access to a wireless network may be gained through the compromise of a wireless device. (Citation: Alexander Bolshev, Gleb Cherbov July 2014) (Citation: Alexander Bolshev March 2014) Adversaries may also utilize radios and other wireless communication devices on the same frequency as the wireless network. Wireless compromise can be done as an initial access vector from a remote distance. 

A Polish student used a modified TV remote controller to gain access to and control over the Lodz city tram system in Poland. (Citation: John Bill May 2017) (Citation: Shelley Smith February 2008) The remote controller device allowed the student to interface with the trams network to modify track settings and override operator control. The adversary may have accomplished this by aligning the controller to the frequency and amplitude of IR control protocol signals. (Citation: Bruce Schneier January 2008) The controller then enabled initial access to the network, allowing the capture and replay of tram signals. (Citation: John Bill May 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0860)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Targeted assets

- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0726 - Detection of Wireless Compromise](../../../Defenses/Detection%20Strategies/DET0726%20-%20Detection%20of%20Wireless%20Compromise.md)

## Mitigations

- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Do not inherently rely on the authenticity provided by the network/link layer (e.g., 802.11, LTE, 802.15.4), as link layer equipment may have long lifespans and protocol vulnerabilities may not be easily patched. Provide defense-in-depth by implementing authenticity within the associated application-layer protocol, or through a network-layer VPN. (Citation: CISA March 2010) Furthermore, ensure communication schemes provide strong replay protection, employing techniques such as timestamps or cryptographic nonces. [CISA March 2010](https://us-cert.cisa.gov/ncas/tips/ST05-003)
- [M0808 - Encrypt Network Traffic](../../../Defenses/Mitigations/M0808%20-%20Encrypt%20Network%20Traffic.md) — Utilize strong cryptographic techniques and protocols to prevent eavesdropping on network communications.
- [M0806 - Minimize Wireless Signal Propagation](../../../Defenses/Mitigations/M0806%20-%20Minimize%20Wireless%20Signal%20Propagation.md) — Techniques can include (i) reducing transmission power on wireless signals, (ii) adjusting antenna gain to prevent extensions beyond organizational boundaries, and (iii) employing RF shielding techniques to block excessive signal propagation. (Citation: DHS National Urban Security Technology Laboratory April 2019) [DHS  National Urban Security Technology Laboratory April 2019](https://www.dhs.gov/sites/default/files/saver-msr-rf-detection_cod-508_10july2019.pdf)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Ensure wireless networks require the authentication of all devices, and that all wireless devices also authenticate network infrastructure devices (i.e., mutual authentication). For defense-in-depth purposes, utilize VPNs or ensure that application-layer protocols also authenticate the system or device. Use protocols that provide strong authentication (e.g., IEEE 802.1X), and enforce basic protections, such as MAC filtering, when stronger cryptographic techniques are not available.

## Procedure examples

- [C0020 - Maroochy Water Breach](../../../Threat%20Intelligence/Campaigns/C0020%20-%20Maroochy%20Water%20Breach.md) — In the [Maroochy Water Breach](https://attack.mitre.org/campaigns/C0020), the adversary used a two-way radio to communicate with and set the frequencies of Maroochy Shire's repeater stations.(Citation: Marshall Abrams July 2008) [Marshall Abrams July 2008](https://www.mitre.org/sites/default/files/pdf/08_1145.pdf)

## Sources

- [Alexander Bolshev March 2014](https://www.slideshare.net/slideshow/17-bolshev-1-13/32178888)
- [Alexander Bolshev, Gleb Cherbov July 2014](https://www.blackhat.com/docs/us-14/materials/us-14-Bolshev-ICSCorsair-How-I-Will-PWN-Your-ERP-Through-4-20mA-Current-Loop-WP.pdf)
- [Bruce Schneier January 2008](https://www.schneier.com/blog/archives/2008/01/hacking_the_pol.html)
- [John Bill May 2017](https://www.londonreconnections.com/2017/hacked-cyber-security-railways/)
- [Shelley Smith February 2008](https://inhomelandsecurity.com/teen_hacker_in_poland_plays_tr/)
