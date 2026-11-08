# AML.T0046 - Spamming AI System with Chaff Data

[MITRE ATLAS](../../../README.md) / [AML.TA0011 - Impact](../README.md)

Adversaries may spam the AI system with chaff data that causes increase in the number of detections.
This can cause analysts at the victim organization to waste time reviewing and correcting incorrect inferences.

Adversaries may also spam AI agents with excessive low-severity auditable events or agentic actions that require a human-in-the-loop, wasting time for the victim organization in human review of the agentic AI system.

**Tactics**  [AML.TA0011 - Impact](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit volume and rate of queries to protect the system from chaff data spam.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Authentication on production models can help prevent anonymous chaff data spam.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0046)
