# AML.T0003 - Search Victim-Owned Websites

[MITRE ATLAS](../../../README.md) / [AML.TA0002 - Reconnaissance](../README.md)

Adversaries may search websites owned by the victim for information that can be used during targeting.
Victim-owned websites may contain technical details about their AI-enabled products or services.
Victim-owned websites may contain a variety of details, including names of departments/divisions, physical locations, and data about key employees such as names, roles, and contact info.
These sites may also have details highlighting business operations and relationships.

Adversaries may search victim-owned websites to gather actionable information.
This information may help adversaries tailor their attacks (e.g. [Adversarial AI Attacks](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.000%20-%20Adversarial%20AI%20Attacks/README.md) or [Manual Modification](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.003%20-%20Manual%20Modification/README.md)).
Information from these sources may reveal opportunities for other forms of reconnaissance (e.g. [Search Open Technical Databases](../AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md) or [Search Open AI Vulnerability Analysis](../AML.T0001%20-%20Search%20Open%20AI%20Vulnerability%20Analysis/README.md))

**Tactics**  [AML.TA0002 - Reconnaissance](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Demonstrated

**ATT&CK mapping**  [Local ATT&CK T1594](../../../../Enterprise/Tactics/01%20TA0043%20-%20Reconnaissance/T1594%20-%20Search%20Victim-Owned%20Websites/README.md) · [MITRE ATT&CK T1594](https://attack.mitre.org/techniques/T1594/)

## Case studies

- [AML.CS0014 - Confusing Antimalware Neural Networks](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md#step-s01)
- [AML.CS0039 - Living Off AI: Prompt Injection via Jira Service Management](../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md#step-s00)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Restrict release of technical information on ML-enabled products and organizational information on the teams supporting ML-enabled products.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0003)
