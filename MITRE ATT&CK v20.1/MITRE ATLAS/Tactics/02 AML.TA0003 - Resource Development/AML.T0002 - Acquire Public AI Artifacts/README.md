# AML.T0002 - Acquire Public AI Artifacts

[MITRE ATLAS](../../../README.md) / [AML.TA0003 - Resource Development](../README.md)

Adversaries may search public sources, including cloud storage, public-facing services, and software or data repositories, to identify AI artifacts.
These AI artifacts may include the software stack used to train and deploy models, training and testing data, model configurations and parameters.
An adversary will be particularly interested in artifacts hosted by or associated with the victim organization as they may represent what that organization uses in a production environment.
Adversaries may identify artifact repositories via other resources associated with the victim organization (e.g. [Search Victim-Owned Websites](../../01%20AML.TA0002%20-%20Reconnaissance/AML.T0003%20-%20Search%20Victim-Owned%20Websites/README.md) or [Search Open Technical Databases](../../01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)).
These AI artifacts often provide adversaries with details of the AI task and approach.

AI artifacts can aid in an adversary's ability to [Replicate AI Model Behavior](../AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md).
If these artifacts include pieces of the actual model in production, they can be used to directly [Craft Adversarial Data](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md).
Acquiring some artifacts requires registration (providing user details such as an email address or name), AWS keys, or written requests, and may require the adversary to [Establish Accounts](../AML.T0021%20-%20Establish%20Accounts/README.md).

Artifacts might be hosted on victim-controlled infrastructure, providing the victim with some information on who has accessed that data.

**Tactics**  [AML.TA0003 - Resource Development](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0002.002 - AI Agent Configuration](AML.T0002.002%20-%20AI%20Agent%20Configuration/README.md)
- [AML.T0002.000 - Datasets](AML.T0002.000%20-%20Datasets/README.md)
- [AML.T0002.001 - Models](AML.T0002.001%20-%20Models/README.md)

## Case studies

- [AML.CS0001 - Botnet Domain Generation Algorithm (DGA) Detection Evasion](../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md#step-s01)
- [AML.CS0006 - ClearviewAI Misconfiguration](../../../Case%20Studies/Incidents/AML.CS0006%20-%20ClearviewAI%20Misconfiguration.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0006%20-%20ClearviewAI%20Misconfiguration.md#step-s02)
- [AML.CS0011 - Microsoft Edge AI Evasion](../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md#step-s01)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Limit the release of sensitive information in the metadata of deployed systems and publicly available applications.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0002)
