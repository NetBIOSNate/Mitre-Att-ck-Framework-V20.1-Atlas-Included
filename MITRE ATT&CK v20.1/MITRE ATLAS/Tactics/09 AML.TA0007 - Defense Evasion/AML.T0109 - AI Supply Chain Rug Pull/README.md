# AML.T0109 - AI Supply Chain Rug Pull

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may publish legitimate AI components or software, gain user adoption, then push an update with a malicious variant, leading to [Supply Chain Compromise](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md). More scrutiny is often placed on a supply chain dependency when it is first being considered for inclusion in an AI system. Performing a rug pull may allow adversaries to bypass these defenses and be more likely to achieve [Initial Access](../../04%20AML.TA0004%20-%20Initial%20Access/README.md).

Adversaries may [Publish Poisoned AI Artifacts](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/README.md), then attempt to gain user trust and increase adoption before performing the rug pull (See [AI Supply Chain Reputation Inflation](../AML.T0111%20-%20AI%20Supply%20Chain%20Reputation%20Inflation/README.md)).

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0053 - Poisoned Postmark MCP Server Email Exfiltration](../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md#step-s03)

## Mitigations

- [AML.M0014 - Verify AI Artifacts](../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Pin dependencies and AI artifacts to approved digests and require approval and verification of each update. Prevent mutable references or automatic updates from bypassing this process.
- [AML.M0023 - Maintain an AI Bill of Materials](../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Retain versioned component and dependency records across updates. Use these records to identify deployments that adopted a subsequently identified malicious release and guide replacement or rollback.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0109)
