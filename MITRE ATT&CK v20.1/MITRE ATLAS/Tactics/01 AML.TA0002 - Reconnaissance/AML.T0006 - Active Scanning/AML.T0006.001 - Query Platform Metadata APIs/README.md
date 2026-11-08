# AML.T0006.001 - Query Platform Metadata APIs

[MITRE ATLAS](../../../../README.md) / [AML.TA0002 - Reconnaissance](../../README.md) / [AML.T0006 - Active Scanning](../README.md)

Adversaries may query documented or undocumented APIs in agentic SaaS hosting platforms to uncover agentic targets. SaaS and agentic platforms can expose provider control-plane or identity APIs that return tenant, environment, or deployment information IDs, including for resources that are misconfigured or unintentionally accessible by unauthenticated users. 

Attackers have been seen abusing this type of functionality to perform information gathering on SaaS platforms, for example via AADInternals' OSINT page, an OSINT online tool showcasing an undocumented API reconnaissance method for Entra ID. This undocumented Power Platform API could be used to uncover environment IDs, which may subsequently be used to scan for public agents. Following the identified abuse, required authentication was added to the tool.

**Tactics**  [AML.TA0002 - Reconnaissance](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md), [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0039 - AI Honeypots](../../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — By capturing adversarial fingerprinting behavior, honeypots can help provide early warning of sweeping activity meant to discover exposed AI targets and attack surfaces being explored by adversaries.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0006.001)
