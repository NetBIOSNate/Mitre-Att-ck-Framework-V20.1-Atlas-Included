# AML.M0017 - AI Model Distribution Methods

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Deploying AI models to edge devices can increase the attack surface of the system.
Consider serving models in the cloud to reduce the level of access the adversary has to the model.
Also consider computing features in the cloud to prevent gray-box attacks, where an adversary has access to the model preprocessing methods.

**Mitigation categories**  Policy

**Lifecycle phases**  Deployment

## Techniques mitigated

- [AML.T0010.003 - Model Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md) — An adversary could repackage the application with a malicious version of the model.
- [AML.T0035 - AI Artifact Collection](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md) — Avoiding the deployment of models to edge devices reduces the attack surface and can prevent adversary artifact collection.
- [AML.T0043.000 - White-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.000%20-%20White-Box%20Optimization/README.md) — With full access to the model, an adversary could perform white-box attacks.
- [AML.T0044 - Full AI Model Access](../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0044%20-%20Full%20AI%20Model%20Access/README.md) — Not distributing the model in software to edge devices, can limit an adversary's ability to gain full access to the model.
- [AML.T0048.004 - AI Intellectual Property Theft](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md) — Avoiding  the deployment of models to edge devices reduces an adversary's potential access to models or AI artifacts.
- [AML.T0063 - Discover AI Model Outputs](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0063%20-%20Discover%20AI%20Model%20Outputs/README.md) — Avoiding the deployment of models to edge devices reduces an adversary's ability to collect sensitive information about the model outputs.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0017)
