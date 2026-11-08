# AML.M0006 - Predictive AI Ensembles

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Use an ensemble of diverse predictive AI models to reduce reliance on a single model or model family and improve robustness against adversarial examples.

Ensemble members should be sufficiently diverse, such as through different architectures, training procedures, features, or model families. Combine their predictions using an aggregation or adjudication method designed to prevent an adversarial example that evades one model from controlling the system's predictions.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  AI Model Engineering

## Techniques mitigated

- [AML.T0014 - Discover AI Model Family](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0014%20-%20Discover%20AI%20Model%20Family/README.md) — Use multiple different models to fool adversaries of which type of model is used and how the model used.
- [AML.T0015 - Evade AI Model](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md) — Using multiple different models increases robustness to attack.
- [AML.T0031 - Erode AI Model Integrity](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md) — Using multiple different models increases robustness to attack.
- [AML.T0043 - Craft Adversarial Data](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.T0043.000 - White-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.000%20-%20White-Box%20Optimization/README.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.T0043.001 - Black-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.T0043.002 - Black-Box Transfer](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.002%20-%20Black-Box%20Transfer/README.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.T0043.003 - Manual Modification](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.003%20-%20Manual%20Modification/README.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.T0043.004 - Insert Backdoor Trigger](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.004%20-%20Insert%20Backdoor%20Trigger/README.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0006)
