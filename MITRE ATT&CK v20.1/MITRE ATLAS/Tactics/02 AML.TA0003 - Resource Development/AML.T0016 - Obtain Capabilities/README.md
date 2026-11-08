# AML.T0016 - Obtain Capabilities

[MITRE ATLAS](../../../README.md) / [AML.TA0003 - Resource Development](../README.md)

Adversaries may search for and obtain software capabilities for use in their operations.
Capabilities may be specific to AI-based attacks [Adversarial AI Attack Implementations](AML.T0016.000%20-%20Adversarial%20AI%20Attack%20Implementations/README.md) or generic software tools repurposed for malicious intent ([Software Tools](AML.T0016.001%20-%20Software%20Tools/README.md)). In both instances, an adversary may modify or customize the capability to aid in targeting a particular AI-enabled system.

**Tactics**  [AML.TA0003 - Resource Development](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1588](../../../../Enterprise/Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/README.md) · [MITRE ATT&CK T1588](https://attack.mitre.org/techniques/T1588/)

## Sub-techniques

- [AML.T0016.000 - Adversarial AI Attack Implementations](AML.T0016.000%20-%20Adversarial%20AI%20Attack%20Implementations/README.md)
- [AML.T0016.004 - AI Agent Tools](AML.T0016.004%20-%20AI%20Agent%20Tools/README.md)
- [AML.T0016.003 - Exploits](AML.T0016.003%20-%20Exploits/README.md)
- [AML.T0016.002 - Generative AI](AML.T0016.002%20-%20Generative%20AI/README.md)
- [AML.T0016.001 - Software Tools](AML.T0016.001%20-%20Software%20Tools/README.md)

## Case studies

- [AML.CS0033 - Live Deepfake Image Injection to Evade Mobile KYC Verification](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md#step-s03)
- [AML.CS0072 - AI Recommendation Poisoning via Crafted AI Assistant Links](../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md) · [S00](../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md#step-s00)

## Mitigations

- [AML.M0001 - Limit Model Artifact Release](../../../Mitigations/AML.M0001%20-%20Limit%20Model%20Artifact%20Release.md) — Limit public release of production model artifacts that adversaries could acquire and adapt as operational capabilities.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0016)
