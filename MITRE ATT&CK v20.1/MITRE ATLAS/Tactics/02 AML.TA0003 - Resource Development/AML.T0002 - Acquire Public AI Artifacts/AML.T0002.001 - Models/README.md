# AML.T0002.001 - Models

[MITRE ATLAS](../../../../README.md) / [AML.TA0003 - Resource Development](../../README.md) / [AML.T0002 - Acquire Public AI Artifacts](../README.md)

Adversaries may acquire public models to use in their operations.
Adversaries may seek models used by the victim organization or models that are representative of those used by the victim organization.
Representative models may include model architectures, or pre-trained models which define the architecture as well as model parameters from training on a dataset.
The adversary may search public sources for common model architecture configuration file formats such as YAML or Python configuration files, and common model storage file formats such as ONNX (.onnx), HDF5 (.h5), Pickle (.pkl), PyTorch (.pth), or TensorFlow (.pb, .tflite).

Acquired models are useful in advancing the adversary's operations and are frequently used to tailor attacks to the victim model.

**Tactics**  [AML.TA0003 - Resource Development](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0005 - Attack on Machine Translation Services](../../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md#step-s02)
- [AML.CS0007 - GPT-2 Model Replication](../../../../Case%20Studies/Exercises/AML.CS0007%20-%20GPT-2%20Model%20Replication.md) · [S01](../../../../Case%20Studies/Exercises/AML.CS0007%20-%20GPT-2%20Model%20Replication.md#step-s01)
- [AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps](../../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md) · [S01](../../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md#step-s01)
- [AML.CS0019 - PoisonGPT](../../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md) · [S00](../../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md#step-s00)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S00](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s00)

## Mitigations

- [AML.M0001 - Limit Model Artifact Release](../../../../Mitigations/AML.M0001%20-%20Limit%20Model%20Artifact%20Release.md) — Limiting the release of model architectures and checkpoints can reduce an adversary's ability to target those models.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0002.001)
