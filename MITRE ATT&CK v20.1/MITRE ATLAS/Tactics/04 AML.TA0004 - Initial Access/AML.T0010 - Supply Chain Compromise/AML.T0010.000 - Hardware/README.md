# AML.T0010.000 - Hardware

[MITRE ATLAS](../../../../README.md) / [AML.TA0004 - Initial Access](../../README.md) / [AML.T0010 - Supply Chain Compromise](../README.md)

Adversaries may target AI systems by disrupting or manipulating the hardware supply chain. AI models often run on specialized hardware such as GPUs, TPUs, or embedded devices, but may also be optimized to operate on CPUs.

**Tactics**  [AML.TA0004 - Initial Access](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

**ATT&CK mapping**  [Local ATT&CK T1195.003](../../../../../Enterprise/Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.003%20-%20Compromise%20Hardware%20Supply%20Chain/README.md) · [MITRE ATT&CK T1195.003](https://attack.mitre.org/techniques/T1195/003/)

## Mitigations

- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on compromised hardware suppliers and products, including affected models and production batches where known. Use this intelligence to identify affected hardware, prevent its introduction into downstream systems, and prioritize investigation and replacement.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0010.000)
