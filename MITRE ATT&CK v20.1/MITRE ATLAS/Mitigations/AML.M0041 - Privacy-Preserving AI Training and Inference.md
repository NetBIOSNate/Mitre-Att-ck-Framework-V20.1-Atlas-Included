# AML.M0041 - Privacy-Preserving AI Training and Inference

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Use privacy-preserving mechanisms throughout model training and inference to limit disclosure of sensitive training or inference data. These mechanisms can reduce the risk that model outputs reveal sensitive information, such as individual training records, and can also protect sensitive training data from exposure to model developers or operators.

Methods that improve privacy in model outputs include Differential Privacy (DP), which provides a formal privacy guarantee limiting how much an individual's data can influence outputs. DP can be applied during training, by adding calibrated noise to clipped gradients, or to inference outputs. Ensuring that models do not overfit during training is also a strategy for limiting model memorization of individual records and improving privacy in deployment.

Other privacy-preserving mechanisms can protect data from exposure to developers and operators during training and inference. Federated Learning enables training without revealing training data to training participants. Secure Multi-Party Computation (SMPC) and Homomorphic Encryption can both protect training data from exposure to training participants and also can protect inference inputs from exposure to model operators. These mechanisms by themselves do not prevent disclosure through a deployed model's outputs, but can be combined with DP as a combined strategy [google](https://research.google/blog/distributed-differential-privacy-for-federated-learning/).

**Mitigation categories**  Technical - AI

**Lifecycle phases**  AI Model Engineering, AI Model Evaluation, Deployment

## Techniques mitigated

- [AML.T0137 - Training Data Information from AI Models](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/README.md) — Use privacy-preserving mechanisms to limit how much individual training data influences model behavior and outputs, reducing disclosure of sensitive information about the data used to train or fine-tune the model.
- [AML.T0137.000 - Infer Membership](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.000%20-%20Infer%20Membership/README.md) — Use privacy-preserving mechanisms to limit how much an individual sample's inclusion in training influences model behavior and outputs, reducing the ability to infer whether that sample was used.
- [AML.T0137.001 - Infer Properties](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.001%20-%20Infer%20Properties/README.md) — Use privacy-preserving mechanisms to limit information about training data reflected in model behavior and outputs, reducing the ability to infer its aggregate properties.
- [AML.T0137.002 - Invert AI Model](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.002%20-%20Invert%20AI%20Model/README.md) — Use privacy-preserving mechanisms to limit information about training data reflected in model behavior and outputs, reducing the ability to infer sensitive attributes or reconstruct representative examples.
- [AML.T0137.003 - Extract Memorized Data](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.003%20-%20Extract%20Memorized%20Data/README.md) — Use privacy-preserving mechanisms to limit model memorization of individual training records and their influence on outputs, reducing the ability to elicit training content.

## References

- [Distributed differential privacy for federated learning](https://research.google/blog/distributed-differential-privacy-for-federated-learning/)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0041)
