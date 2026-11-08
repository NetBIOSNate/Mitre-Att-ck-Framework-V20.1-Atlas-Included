# AML.M0010 - Predictive AI Input Restoration

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Preprocess predictive AI inference inputs to remove, reduce, or disrupt adversarial perturbations before the inputs are evaluated by the model.

Restoration methods may include denoising, compression, reconstruction, resampling, feature squeezing, randomized transformations, or other modality-appropriate preprocessing. Evaluate restoration methods against adaptive adversaries that account for the preprocessing operation.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Data Preparation, AI Model Evaluation, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0015 - Evade AI Model](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md) — Preprocessing model inputs can prevent malicious data from going through the machine learning pipeline.
- [AML.T0031 - Erode AI Model Integrity](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md) — Preprocessing model inputs can prevent malicious data from going through the machine learning pipeline.
- [AML.T0043 - Craft Adversarial Data](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) — Input restoration can help remediate adversarial inputs.
- [AML.T0043.000 - White-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.000%20-%20White-Box%20Optimization/README.md) — Input restoration can help remediate adversarial inputs.
- [AML.T0043.001 - Black-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md) — Input restoration adds an extra layer of unknowns and randomness when an adversary evaluates the input-output relationship.
- [AML.T0043.002 - Black-Box Transfer](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.002%20-%20Black-Box%20Transfer/README.md) — Input restoration can help remediate adversarial inputs.
- [AML.T0043.003 - Manual Modification](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.003%20-%20Manual%20Modification/README.md) — Input restoration can help remediate adversarial inputs.
- [AML.T0043.004 - Insert Backdoor Trigger](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.004%20-%20Insert%20Backdoor%20Trigger/README.md) — Input restoration can help remediate adversarial inputs.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0010)
