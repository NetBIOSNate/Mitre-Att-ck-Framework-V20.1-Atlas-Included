# AML.T0112.001 - AI Artifacts

[MITRE ATLAS](../../../../README.md) / [AML.TA0011 - Impact](../../README.md) / [AML.T0112 - Machine Compromise](../README.md)

Adversaries may achieve full system compromise by introducing malicious AI artifacts, such as models or data, that contain embedded malware or other malicious commands. AI artifacts are often stored in model registries or data stores and may affect many systems that pull these resources.

Malicious content stored in AI artifacts may be executed as a result of unsafe serialization formats (e.g. Python pickle) or by other bundled scripts or notebooks.

**Tactics**  [AML.TA0011 - Impact](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Restrict write access to model registries and AI artifact stores.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0112.001)
