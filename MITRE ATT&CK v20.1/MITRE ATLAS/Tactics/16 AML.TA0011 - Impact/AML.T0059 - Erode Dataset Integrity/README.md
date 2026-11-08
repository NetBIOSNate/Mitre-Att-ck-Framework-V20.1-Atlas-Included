# AML.T0059 - Erode Dataset Integrity

[MITRE ATLAS](../../../README.md) / [AML.TA0011 - Impact](../README.md)

Adversaries may poison or manipulate portions of a dataset to reduce its usefulness, reduce trust, and cause users to waste resources correcting errors.

**Tactics**  [AML.TA0011 - Impact](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0025 - Web-Scale Data Poisoning: Split-View Attack](../../../Case%20Studies/Exercises/AML.CS0025%20-%20Web-Scale%20Data%20Poisoning%20-%20Split-View%20Attack.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0025%20-%20Web-Scale%20Data%20Poisoning%20-%20Split-View%20Attack.md#step-s04)

## Mitigations

- [AML.M0007 - Sanitize Training Data](../../../Mitigations/AML.M0007%20-%20Sanitize%20Training%20Data.md) — Screen samples, labels, annotations, and metadata for manipulation that degrades dataset quality or usefulness. Quarantine and remediate affected data before use.
- [AML.M0025 - Maintain AI Dataset Provenance](../../../Mitigations/AML.M0025%20-%20Maintain%20AI%20Dataset%20Provenance.md) — Maintaining dataset provenance can help identify adverse changes to the data.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0059)
