# T1659 - Content Injection

[Enterprise](../../../README.md) / [Command and Control](../README.md)

Adversaries may gain access and continuously communicate with victims by injecting malicious content into systems through online network traffic. Rather than luring victims to malicious payloads hosted on a compromised website (i.e., [Drive-by Target](https://attack.mitre.org/techniques/T1608/004) followed by [Drive-by Compromise](https://attack.mitre.org/techniques/T1189)), adversaries may initially access victims through compromised data-transfer channels where they can manipulate traffic and/or inject their own content. These compromised online network channels may also be used to deliver additional payloads (i.e., [Ingress Tool Transfer](https://attack.mitre.org/techniques/T1105)) and other data to already compromised systems.(Citation: ESET MoustachedBouncer)

Adversaries may inject content to victim systems in various ways, including:

* From the middle, where the adversary is in-between legitimate online client-server communications (**Note:** this is similar but distinct from [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557), which describes AiTM activity solely within an enterprise environment)(Citation: Kaspersky Encyclopedia MiTM)
* From the side, where malicious content is injected and races to the client as a fake response to requests of a legitimate online server(Citation: Kaspersky ManOnTheSide)

Content injection is often the result of compromised upstream communication channels, for example at the level of an internet service provider (ISP) as is the case with "lawful interception."(Citation: Kaspersky ManOnTheSide)(Citation: ESET MoustachedBouncer)(Citation: EFF China GitHub Attack)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1659)

**Tactics**  [Initial Access](../../03%20TA0001%20-%20Initial%20Access/README.md), [Command and Control](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Where possible, ensure that online traffic is appropriately encrypted through services such as trusted VPNs.
- [M1021 - Restrict Web-Based Content](../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — Consider blocking download/transfer and execution of potentially uncommon file types known to be used in adversary campaigns.

## Procedure examples

- [S1088 - Disco](../../../Threat%20Intelligence/Software/Malware/S1088%20-%20Disco.md) — [Disco](https://attack.mitre.org/software/S1088) has achieved initial access and execution through content injection into DNS, HTTP, and SMB replies to targeted hosts that redirect them to download malicious files.(Citation: MoustachedBouncer ESET August 2023) [MoustachedBouncer ESET August 2023](https://www.welivesecurity.com/en/eset-research/moustachedbouncer-espionage-against-foreign-diplomats-in-belarus/)
- [G1019 - MoustachedBouncer](../../../Threat%20Intelligence/Groups/G1019%20-%20MoustachedBouncer.md) — [MoustachedBouncer](https://attack.mitre.org/groups/G1019) has injected content into DNS, HTTP, and SMB replies to redirect specifically-targeted victims to a fake Windows Update page to download malware.(Citation: MoustachedBouncer ESET August 2023) [MoustachedBouncer ESET August 2023](https://www.welivesecurity.com/en/eset-research/moustachedbouncer-espionage-against-foreign-diplomats-in-belarus/)

## Detection strategies

- [DET0349 - Detection Strategy for Content Injection](../../../Defenses/Detection%20Strategies/DET0349%20-%20Detection%20Strategy%20for%20Content%20Injection.md)

## Sources

- [EFF China GitHub Attack](https://www.eff.org/deeplinks/2015/04/china-uses-unencrypted-websites-to-hijack-browsers-in-github-attack)
- [ESET MoustachedBouncer](https://www.welivesecurity.com/en/eset-research/moustachedbouncer-espionage-against-foreign-diplomats-in-belarus/)
- [Kaspersky Encyclopedia MiTM](https://encyclopedia.kaspersky.com/glossary/man-in-the-middle-attack/)
- [Kaspersky ManOnTheSide](https://usa.kaspersky.com/blog/man-on-the-side/27854/)
