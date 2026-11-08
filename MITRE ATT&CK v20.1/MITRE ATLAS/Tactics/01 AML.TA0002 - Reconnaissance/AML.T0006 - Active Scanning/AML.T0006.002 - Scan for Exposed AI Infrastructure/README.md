# AML.T0006.002 - Scan for Exposed AI Infrastructure

[MITRE ATLAS](../../../../README.md) / [AML.TA0002 - Reconnaissance](../../README.md) / [AML.T0006 - Active Scanning](../README.md)

Adversaries may scan network ports and services to identify deployed AI backends, model-serving endpoints, and AI agent infrastructure reachable over the internet. Self-hosted AI runtimes typically listen on predictable, well-known ports and expose standard API paths, allowing adversaries to efficiently locate candidate hosts and infer the platform running on them. 

After identifying candidate hosts, adversaries can interact with them directly to confirm live AI services, fingerprint the software stack, and determine version and configuration details. This information can be used to select exploitable targets and tailor subsequent access attempts.

**Tactics**  [AML.TA0002 - Reconnaissance](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md), [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0039 - AI Honeypots](../../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — By capturing adversarial fingerprinting behavior, honeypots can help provide early warning of sweeping activity meant to discover exposed AI targets and attack surfaces being explored by adversaries.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0006.002)
