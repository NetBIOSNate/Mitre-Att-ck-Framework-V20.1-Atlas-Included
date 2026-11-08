# AML.T0095 - Search Open Websites/Domains

[MITRE ATLAS](../../../README.md) / [AML.TA0002 - Reconnaissance](../README.md)

Adversaries may search public websites and/or domains for information about victims and AI targets that can be used during targeting and to discover opportunities for successful attacks. Information about a victim's attack surface may be available in various online sites, such as social media, news sites, or domains owned by the victim.

Adversaries may find the information they seek to gather via search engines. They can use precise search queries to identify software platforms or services used by the victim to use in targeting. This may be followed by [Exploit Public-Facing Application](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md) or [Prompt Infiltration via Public-Facing Application](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md).

Adversaries may utilize OSINT-based discovery to map different AI assets by using search engine result pages, as well as backlink analysis, to locate agentic interfaces (which are frequently embedded via iFrames and follow predictable naming conventions). By analyzing the indexed URL structures of these sources from different search engines, attackers can often reverse-engineer internal environment IDs and organization-specific naming conventions. This intelligence gathering significantly narrows the search space for any later targeted fuzzing or enumeration performed by [Active Scanning: Enumerate Hosted AI Resources](../AML.T0006%20-%20Active%20Scanning/AML.T0006.000%20-%20Enumerate%20Hosted%20AI%20Resources/README.md).

**Tactics**  [AML.TA0002 - Reconnaissance](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1593](../../../../Enterprise/Tactics/01%20TA0043%20-%20Reconnaissance/T1593%20-%20Search%20Open%20Websites%20-%20Domains/README.md) · [MITRE ATT&CK T1593](https://attack.mitre.org/techniques/T1593/)

## Sub-techniques

- [AML.T0095.000 - Code Repositories](AML.T0095.000%20-%20Code%20Repositories/README.md)

## Case studies

- [AML.CS0039 - Living Off AI: Prompt Injection via Jira Service Management](../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md#step-s01)
- [AML.CS0061 - AI in the Middle: Web-Based AI Services as C2 Relays](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md#step-s00)
- [AML.CS0065 - Model Namespace Reuse Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md#step-s00)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Limit public technical and organizational information that reveals the AI stack, services, personnel, or other targeting details on websites and domains.
- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Decoy assets, such as honeypots, can act as a first contact for adversarial activity and reveal discovery channels that attackers are using to find web AI assets for targeting.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0095)
