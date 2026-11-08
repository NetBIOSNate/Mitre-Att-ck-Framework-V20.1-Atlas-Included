# T1213.005 - Messaging Applications

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1213 - Data from Information Repositories](../README.md)

Adversaries may leverage chat and messaging applications, such as Microsoft Teams, Google Chat, and Slack, to mine valuable information.  

The following is a brief list of example information that may hold potential value to an adversary and may also be found on messaging applications: 

* Testing / development credentials (i.e., [Chat Messages](https://attack.mitre.org/techniques/T1552/008)) 
* Source code snippets 
* Links to network shares and other internal resources 
* Proprietary data(Citation: Guardian Grand Theft Auto Leak 2022)
* Discussions about ongoing incident response efforts(Citation: SC Magazine Ragnar Locker 2021)(Citation: Microsoft DEV-0537)

In addition to exfiltrating data from messaging applications, adversaries may leverage data from chat messages in order to improve their targeting - for example, by learning more about an environment or evading ongoing incident response efforts.(Citation: Sentinel Labs NullBulge 2024)(Citation: Permiso Scattered Spider 2023)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1213/005)

**Tactics**  [Collection](../../README.md)

**Platforms**  [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has gathered Telegram Desktop messaging data from the applications data directories stored on the victim device to include cryptographic key material, and session mapping files that can recreate a compromised user’s Telegram session on another system.(Citation: Microsoft Sapphire Sleet APR 2026) [Microsoft Sapphire Sleet APR 2026](https://www.microsoft.com/en-us/security/blog/2026/04/16/dissecting-sapphire-sleets-macos-intrusion-from-lure-to-compromise/)
- [G0117 - Fox Kitten](../../../../Threat%20Intelligence/Groups/G0117%20-%20Fox%20Kitten.md) — [Fox Kitten](https://attack.mitre.org/groups/G0117) has accessed victim security and IT environments and Microsoft Teams to mine valuable information.(Citation: CISA AA20-259A Iran-Based Actor September 2020) [CISA AA20-259A Iran-Based Actor September 2020](https://us-cert.cisa.gov/ncas/alerts/aa20-259a)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has searched a victim's network for organization collaboration channels like MS Teams or Slack to discover further high-privilege account credentials.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has browsed Microsoft Teams and downloaded files.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) threat actors search the victim’s Slack and Microsoft Teams for conversations about the intrusion and incident response.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [S9009 - TruffleHog](../../../../Threat%20Intelligence/Software/Tools/S9009%20-%20TruffleHog.md) — [TruffleHog](https://attack.mitre.org/software/S9009) has obtained data and credentials associated with messaging applications to include Slack.(Citation: Github TruffleSecurity Trufflehog April 2025) [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Preemptively search through communication services to find inappropriately shared data, and take actions to reduce exposure when found.
- [M1060 - Out-of-Band Communications Channel](../../../../Defenses/Mitigations/M1060%20-%20Out-of-Band%20Communications%20Channel.md) — Implement secure out-of-band communication channels to use as an alternative to in-network chat applications during a security incident. This ensures that critical communications remain secure even if primary messaging channels are compromised by adversaries.(Citation: TrustedSec OOB Communications) [TrustedSec OOB Communications](https://trustedsec.com/blog/to-oob-or-not-to-oob-why-out-of-band-communications-are-essential-for-incident-response)
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Develop and publish policies that define acceptable information to be posted in chat applications.

## Detection strategies

- [DET0567 - Detecting Unauthorized Collection from Messaging Applications in SaaS and Office Environments](../../../../Defenses/Detection%20Strategies/DET0567%20-%20Detecting%20Unauthorized%20Collection%20from%20Messaging%20Applications%20in%20SaaS%20and%20Office%20Envi.md)

## Sources

- [Sentinel Labs NullBulge 2024](https://www.sentinelone.com/labs/nullbulge-threat-actor-masquerades-as-hacktivist-group-rebelling-against-ai/)
- [Permiso Scattered Spider 2023](https://permiso.io/blog/lucr-3-scattered-spider-getting-saas-y-in-the-cloud)
- [SC Magazine Ragnar Locker 2021](https://www.scmagazine.com/analysis/ragnar-locker-reminds-breach-victims-it-can-read-the-on-network-incident-response-chat-rooms)
- [Guardian Grand Theft Auto Leak 2022](https://www.theguardian.com/games/2022/sep/19/grand-theft-auto-6-leak-who-hacked-rockstar-and-what-was-stolen)
- [Microsoft DEV-0537](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
