# T1639 - Exfiltration Over Alternative Protocol

[Mobile](../../../README.md) / [Exfiltration](../README.md)

Adversaries may steal data by exfiltrating it over a different protocol than that of the existing command and control channel. The data may also be sent to an alternate network location from the main command and control server. 

Alternate protocols include FTP, SMTP, HTTP/S, DNS, SMB, or any other network protocol not being used as the main command and control channel. Different protocol channels could also include Web services such as cloud storage. Adversaries may opt to also encrypt and/or obfuscate these alternate channels.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1639)

**Tactics**  [Exfiltration](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1639.001 - Exfiltration Over Unencrypted Non-C2 Protocol](T1639.001%20-%20Exfiltration%20Over%20Unencrypted%20Non-C2%20Protocol/README.md)

## Detection strategies

- [DET0698 - Detection of Exfiltration Over Alternative Protocol](../../../Defenses/Detection%20Strategies/DET0698%20-%20Detection%20of%20Exfiltration%20Over%20Alternative%20Protocol.md)

## Procedure examples

- [S1056 - TianySpy](../../../Threat%20Intelligence/Software/Malware/S1056%20-%20TianySpy.md) — [TianySpy](https://attack.mitre.org/software/S1056) can exfiltrate collected user data, including credentials and authorized cookies, via email.(Citation: trendmicro_tianyspy_0122) [trendmicro_tianyspy_0122](https://www.trendmicro.com/en_us/research/22/a/tianyspy-malware-uses-smishing-disguised-as-message-from-telco.html)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-30.html)
