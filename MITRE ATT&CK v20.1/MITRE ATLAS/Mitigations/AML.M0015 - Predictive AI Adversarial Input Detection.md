# AML.M0015 - Predictive AI Adversarial Input Detection

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Detect and block digital or physical adversarial examples submitted to predictive AI models. Adversarial examples are inputs modified or constructed to cause misclassification, missed detection, excessive computation, or another attacker-selected behavior.

Apply detection before model inference and monitor for input characteristics or query patterns associated with adversarial example generation, transfer attacks, or black-box optimization. Detection may use statistical tests, auxiliary models, consistency checks, input distribution analysis, or modality-specific adversarial example detectors.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Data Preparation, AI Model Engineering, AI Model Evaluation, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0015 - Evade AI Model](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md) — Prevent an attacker from introducing adversarial data into the system.
- [AML.T0029 - Denial of AI Service](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0029%20-%20Denial%20of%20AI%20Service/README.md) — Assess queries before inference call or enforce timeout policy for queries which consume excessive resources.
- [AML.T0031 - Erode AI Model Integrity](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md) — Incorporate adversarial input detection into the pipeline before inputs reach the model.
- [AML.T0043 - Craft Adversarial Data](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) — Incorporate adversarial input detection to block malicious inputs at inference time.
- [AML.T0043.000 - White-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.000%20-%20White-Box%20Optimization/README.md) — Incorporate adversarial input detection to block malicious inputs at inference time.
- [AML.T0043.001 - Black-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md) — Monitor queries and query patterns to the target model, block access if suspicious queries are detected.
- [AML.T0043.002 - Black-Box Transfer](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.002%20-%20Black-Box%20Transfer/README.md) — Incorporate adversarial input detection to block malicious inputs at inference time.
- [AML.T0043.003 - Manual Modification](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.003%20-%20Manual%20Modification/README.md) — Incorporate adversarial input detection to block malicious inputs at inference time.
- [AML.T0043.004 - Insert Backdoor Trigger](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.004%20-%20Insert%20Backdoor%20Trigger/README.md) — Incorporate adversarial input detection to block malicious inputs at inference time.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0015)
