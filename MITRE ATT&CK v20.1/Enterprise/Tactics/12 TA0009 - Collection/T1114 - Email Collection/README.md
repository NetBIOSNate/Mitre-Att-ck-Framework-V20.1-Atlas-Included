# T1114 - Email Collection

[Enterprise](../../../README.md) / [Collection](../README.md)

Adversaries may target user email to collect sensitive information. Emails may contain sensitive data, including trade secrets or personal information, that can prove valuable to adversaries. Emails may also contain details of ongoing incident response operations, which may allow adversaries to adjust their techniques in order to maintain persistence or evade defenses.(Citation: TrustedSec OOB Communications)(Citation: CISA AA20-352A 2021) Adversaries can collect or forward email from mail servers or clients.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1114)

**Tactics**  [Collection](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md), [Linux](../../../Platforms/Linux.md), [Office Suite](../../../Platforms/Office%20Suite.md)

## Sub-techniques

- [T1114.003 - Email Forwarding Rule](T1114.003%20-%20Email%20Forwarding%20Rule/README.md)
- [T1114.001 - Local Email Collection](T1114.001%20-%20Local%20Email%20Collection/README.md)
- [T1114.002 - Remote Email Collection](T1114.002%20-%20Remote%20Email%20Collection/README.md)

## Procedure examples

- [G1003 - Ember Bear](../../../Threat%20Intelligence/Groups/G1003%20-%20Ember%20Bear.md) — [Ember Bear](https://attack.mitre.org/groups/G1003) attempts to collect mail from accessed systems and servers.(Citation: Cadet Blizzard emerges as novel threat actor)(Citation: CISA GRU29155 2024) [Cadet Blizzard emerges as novel threat actor](https://www.microsoft.com/en-us/security/blog/2023/06/14/cadet-blizzard-emerges-as-a-novel-and-distinct-russian-threat-actor/) · [CISA GRU29155 2024](https://www.cisa.gov/sites/default/files/2024-09/aa24-249a-russian-military-cyber-actors-target-us-and-global-critical-infrastructure.pdf)
- [S0367 - Emotet](../../../Threat%20Intelligence/Software/Malware/S0367%20-%20Emotet.md) — [Emotet](https://attack.mitre.org/software/S0367) has been observed leveraging a module that can scrape email addresses from Outlook.(Citation: CIS Emotet Dec 2018)(Citation: IBM IcedID November 2017)(Citation: Binary Defense Emotes Wi-Fi Spreader) [Binary Defense Emotes Wi-Fi Spreader](https://www.binarydefense.com/resources/blog/emotet-evolves-with-new-wi-fi-spreader/) · [CIS Emotet Dec 2018](https://www.cisecurity.org/white-papers/ms-isac-security-primer-emotet/) · [IBM IcedID November 2017](https://securityintelligence.com/new-banking-trojan-icedid-discovered-by-ibm-x-force-research/)
- [G0059 - Magic Hound](../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has compromised email credentials in order to steal sensitive data.(Citation: Certfa Charming Kitten January 2021) [Certfa Charming Kitten January 2021](https://blog.certfa.com/posts/charming-kitten-christmas-gift/)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) searched the victim’s Microsoft Exchange for emails about the intrusion and incident response.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [G0122 - Silent Librarian](../../../Threat%20Intelligence/Groups/G0122%20-%20Silent%20Librarian.md) — [Silent Librarian](https://attack.mitre.org/groups/G0122) has exfiltrated entire mailboxes from compromised accounts.(Citation: DOJ Iran Indictments March 2018) [DOJ Iran Indictments March 2018](https://www.justice.gov/usao-sdny/press-release/file/1045781/download)
- [S1201 - TRANSLATEXT](../../../Threat%20Intelligence/Software/Malware/S1201%20-%20TRANSLATEXT.md) — [TRANSLATEXT](https://attack.mitre.org/software/S1201) has exfiltrated collected email addresses to the C2 server.(Citation: Zscaler Kimsuky TRANSLATEXT) [Zscaler Kimsuky TRANSLATEXT](https://www.zscaler.com/blogs/security-research/kimsuky-deploys-translatext-target-south-korean-academia#technical-analysis)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Enterprise email solutions have monitoring mechanisms that may include the ability to audit auto-forwarding rules on a regular basis. In an Exchange environment, Administrators can use Get-InboxRule to discover and remove potentially malicious auto-forwarding rules.(Citation: Microsoft Tim McMichael Exchange Mail Forwarding 2) [Microsoft Tim McMichael Exchange Mail Forwarding 2](https://blogs.technet.microsoft.com/timmcmic/2015/06/08/exchange-and-office-365-mail-forwarding-2/)
- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Use of encryption provides an added layer of security to sensitive information sent over email. Encryption using public key cryptography requires the adversary to obtain the private certificate along with an encryption key to decrypt messages.
- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use of multi-factor authentication for public-facing webmail servers is a recommended best practice to minimize the usefulness of usernames and passwords to adversaries.
- [M1060 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M1060%20-%20Out-of-Band%20Communications%20Channel.md) — Use secure out-of-band authentication methods to verify the authenticity of critical actions initiated via email, such as password resets, financial transactions, or access requests. For highly sensitive information, utilize out-of-band communication channels instead of relying solely on email to prevent adversaries from collecting data through compromised email accounts.(Citation: TrustedSec OOB Communications) [TrustedSec OOB Communications](https://trustedsec.com/blog/to-oob-or-not-to-oob-why-out-of-band-communications-are-essential-for-incident-response)

## Detection strategies

- [DET0476 - Email Collection via Local Email Access and Auto-Forwarding Behavior](../../../Defenses/Detection%20Strategies/DET0476%20-%20Email%20Collection%20via%20Local%20Email%20Access%20and%20Auto-Forwarding%20Behavior.md)

## Sources

- [CISA AA20-352A 2021](https://www.cisa.gov/news-events/cybersecurity-advisories/aa20-352a)
- [Microsoft Tim McMichael Exchange Mail Forwarding 2](https://blogs.technet.microsoft.com/timmcmic/2015/06/08/exchange-and-office-365-mail-forwarding-2/)
- [TrustedSec OOB Communications](https://trustedsec.com/blog/to-oob-or-not-to-oob-why-out-of-band-communications-are-essential-for-incident-response)
