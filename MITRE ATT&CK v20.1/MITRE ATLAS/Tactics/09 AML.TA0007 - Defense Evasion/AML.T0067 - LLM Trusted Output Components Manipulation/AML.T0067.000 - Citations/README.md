# AML.T0067.000 - Citations

[MITRE ATLAS](../../../../README.md) / [AML.TA0007 - Defense Evasion](../../README.md) / [AML.T0067 - LLM Trusted Output Components Manipulation](../README.md)

Adversaries may manipulate the citations provided in an AI system's response, in order to make it appear trustworthy. Variants include providing the wrong citation, making up a new citation, or providing the right citation but for adversary-provided data.

**Tactics**  [AML.TA0007 - Defense Evasion](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S12](../../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s12)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Verify that generated citations resolve to the referenced sources and support the associated claims. Preserve source provenance and reject fabricated, mismatched, or misleading citations.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0067.000)
