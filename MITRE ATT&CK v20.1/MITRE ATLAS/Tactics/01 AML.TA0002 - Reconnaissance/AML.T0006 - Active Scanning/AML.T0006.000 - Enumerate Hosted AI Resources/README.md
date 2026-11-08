# AML.T0006.000 - Enumerate Hosted AI Resources

[MITRE ATLAS](../../../../README.md) / [AML.TA0002 - Reconnaissance](../../README.md) / [AML.T0006 - Active Scanning](../README.md)

Adversaries may directly probe an agentic or SaaS platform to enumerate the resources a specific victim has deployed on it. Platforms frequently host AI agents behind predictable URL structures derived from identifiers such as environment, tenant, resource-group, or agent names, and default out-of-the-box deployment configurations keep these conventions consistent across victims. Adversaries can learn these conventions from public sources such as vendor documentation, code repositories and actual hosted resources, then fuzz or brute-force the derived namespace to discover live AI agents, endpoints, and associated metadata. Discovered resources can be used to identify targets for further access, collection, or attack adaptation.

**Tactics**  [AML.TA0002 - Reconnaissance](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md), [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0039 - AI Honeypots](../../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — By capturing adversarial fingerprinting behavior, honeypots can help provide early warning of sweeping activity meant to discover exposed AI targets and attack surfaces being explored by adversaries.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0006.000)
