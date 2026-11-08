# AML.T0024 - Exfiltration via AI Inference API

[MITRE ATLAS](../../../README.md) / [AML.TA0010 - Exfiltration](../README.md)

Adversaries may exfiltrate information from a victim-controlled AI model or service through responses returned by its inference API. Transferred information may include predictions, scores, embeddings, generated content (e.g. text or images), or other sensitive information disclosed in model responses. Responses may be received directly or relayed through an intermediary.

Adversaries may submit inputs designed to cause information to be returned through ordinary API response fields or streaming outputs. The inference API response serves as the transfer channel, including when adversaries use valid accounts or credentials to obtain responses as part of an unauthorized extraction operation.

Received responses may be gathered as [Outputs from AI Models](../../13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md), analyzed to obtain [Training Data Information from AI Models](../../13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/README.md), used to [Craft Adversarial Data](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md), or to [Replicate Behavior from Model Outputs](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md).

**Tactics**  [AML.TA0010 - Exfiltration](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0056 - Model Distillation Campaigns Targeting Anthropic Claude](../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md#step-s04)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S07](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s07)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S10](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s10)

## Mitigations

- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit the volume of API queries in a given period of time to regulate the amount and fidelity of potentially sensitive information an attacker can learn.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Adversaries can use unrestricted API access to build a proxy training dataset and reveal private information.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help identify if sensitive data has been exfiltrated.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Exercise inference interfaces for membership inference, model inversion, and functional extraction. Use findings to improve privacy controls, authentication, output restriction, rate limits, and monitoring.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0024)
