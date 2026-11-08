# AML.T0040 - AI Model Inference API Access

[MITRE ATLAS](../../../README.md) / [AML.TA0000 - AI Model Access](../README.md)

Adversaries may gain access to a model via legitimate access to the inference API.
Inference API access can be a source of information to the adversary ([Discover AI Model Ontology](../../11%20AML.TA0008%20-%20Discovery/AML.T0013%20-%20Discover%20AI%20Model%20Ontology/README.md), [Discover AI Model Family](../../11%20AML.TA0008%20-%20Discovery/AML.T0014%20-%20Discover%20AI%20Model%20Family/README.md)), a means of staging the attack ([Verify Attack](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md), [Craft Adversarial Data](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md)), or for introducing data to the target system for Impact ([Evade AI Model](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md), [Erode AI Model Integrity](../../16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md)).

Many systems rely on the same models provided via an inference API, which means they share the same vulnerabilities. This is especially true of foundation models which are prohibitively resource intensive to train. Adversaries may use their access to model APIs to identify vulnerabilities such as jailbreaks or hallucinations and then target applications that use the same models.

**Tactics**  [AML.TA0000 - AI Model Access](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0010 - Microsoft Azure Service Disruption](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md#step-s05)
- [AML.CS0011 - Microsoft Edge AI Evasion](../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md#step-s02)
- [AML.CS0012 - Face Identification System Evasion via Physical Countermeasures](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md#step-s02)
- [AML.CS0022 - ChatGPT Package Hallucination](../../../Case%20Studies/Exercises/AML.CS0022%20-%20ChatGPT%20Package%20Hallucination.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0022%20-%20ChatGPT%20Package%20Hallucination.md#step-s00)
- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s00)
- [AML.CS0057 - Storm-2139 Azure OpenAI Guardrail Bypass](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md#step-s04)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s01)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s04)

## Mitigations

- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Adversaries can use unrestricted API access to gain information about a production system, stage attacks, and introduce malicious data to the system.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help audit API usage of the model.
- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Honeypots capture which endpoints adversaries are targeting and how they use discovered inference APIs: the models they're interested in, the parameters they use, and the payloads they submit once they reach a live endpoint.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0040)
