# T1090.004 - Domain Fronting

[Enterprise](../../../../README.md) / [Command and Control](../../README.md) / [T1090 - Proxy](../README.md)

Adversaries may take advantage of routing schemes in Content Delivery Networks (CDNs) and other services which host multiple domains to obfuscate the intended destination of HTTPS traffic or traffic tunneled through HTTPS.(Citation: Fifield Blocking Resistent Communication through domain fronting 2015) Domain fronting involves using different domain names in the SNI field of the TLS header and the Host field of the HTTP header. If both domains are served from the same CDN, then the CDN may route to the address specified in the HTTP header after unwrapping the TLS header. A variation of the technique, "domainless" fronting, utilizes a SNI field that is left blank; this may allow the fronting to work even when the CDN attempts to validate that the SNI and HTTP Host fields match (if the blank SNI fields are ignored).

For example, if domain-x and domain-y are customers of the same CDN, it is possible to place domain-x in the TLS header and domain-y in the HTTP header. Traffic will appear to be going to domain-x; however, the CDN may route it to domain-y.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1090/004)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md), [ESXi](../../../../Platforms/ESXi.md)

## Procedure examples

- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has used the meek domain fronting plugin for [Tor](https://attack.mitre.org/software/S0183) to hide the destination of C2 traffic.(Citation: Mandiant No Easy Breach) [Mandiant No Easy Breach](https://www.slideshare.net/slideshow/no-easy-breach-derby-con-2016/66447908)
- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) has the ability to accept a value for HTTP Host Header to enable domain fronting.(Citation: Cobalt Strike Manual 4.3 November 2020) [Cobalt Strike Manual 4.3 November 2020](https://web.archive.org/web/20210708035426/https://www.cobaltstrike.com/downloads/csmanual43.pdf)
- [S0175 - meek](../../../../Threat%20Intelligence/Software/Tools/S0175%20-%20meek.md) — [meek](https://attack.mitre.org/software/S0175) uses Domain Fronting to disguise the destination of network traffic as another server that is hosted in the same Content Delivery Network (CDN) as the intended destination.
- [S0699 - Mythic](../../../../Threat%20Intelligence/Software/Tools/S0699%20-%20Mythic.md) — [Mythic](https://attack.mitre.org/software/S0699) supports domain fronting via custom request headers.(Citation: Mythc Documentation) [Mythc Documentation](https://docs.mythic-c2.net/)
- [S0649 - SMOKEDHAM](../../../../Threat%20Intelligence/Software/Malware/S0649%20-%20SMOKEDHAM.md) — [SMOKEDHAM](https://attack.mitre.org/software/S0649) has used a fronted domain to obfuscate its hard-coded C2 server domain.(Citation: FireEye SMOKEDHAM June 2021) [FireEye SMOKEDHAM June 2021](https://www.fireeye.com/blog/threat-research/2021/06/darkside-affiliate-supply-chain-software-compromise.html)

## Detection strategies

- [DET0196 - Domain Fronting Behavior via Mismatched TLS SNI and HTTP Host Headers](../../../../Defenses/Detection%20Strategies/DET0196%20-%20Domain%20Fronting%20Behavior%20via%20Mismatched%20TLS%20SNI%20and%20HTTP%20Host%20Headers.md)

## Mitigations

- [M1020 - SSL/TLS Inspection](../../../../Defenses/Mitigations/M1020%20-%20SSL%20-%20TLS%20Inspection.md) — If it is possible to inspect HTTPS traffic, the captures can be analyzed for connections that appear to be domain fronting.

## Sources

- [Fifield Blocking Resistent Communication through domain fronting 2015](http://www.icir.org/vern/papers/meek-PETS-2015.pdf)
