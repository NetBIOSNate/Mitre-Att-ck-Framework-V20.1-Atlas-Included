# AML.T0140 - Centralized AI Service Request Routing

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may distribute coordinated AI service requests across multiple pathways to impede detection, conceal the coordinated nature of the requests, and evade AI provider enforcement. Distributing activity can limit the portion of an operation visible through any individual account or pathway, obscuring its aggregate scale and common objective.

Adversaries may use centralized routing infrastructure to divide a workload or prompt suite across multiple pathways, including various service APIs, cloud-hosted endpoints, third-party aggregators or relays, and account pools. Routers may rotate identities and request pathways, mix adversarial requests with unrelated customer traffic, and automatically redirect requests when requests are blocked. These capabilities allow adversaries to maintain coordinated operations while making the activity appear to originate from unrelated users or services.

Adversaries may also use routing infrastructure to centrally optimize API costs and sustain distributed operations within available quotas and budgets. This may include prioritizing cost-efficient access pathways, allocating quotas across accounts to align with operational budgets, segmenting accounts by purpose, and organizing requests to maximize cache reuse. Centralized routing may coordinate shifts across accounts, providers, or pathways in response to pricing or rate-limit changes, enabling an operation to adapt while continuing to obscure its common control and aggregate activity.

This behavior may be implemented via proxy services (See  [Acquire Infrastructure: AI Service Proxies](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md)), multiple cloud instances, IP pools, coordination across multiple accounts, or other distributed infrastructure.

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0056 - Model Distillation Campaigns Targeting Anthropic Claude](../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md#step-s03)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s05)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s04)

## Mitigations

- [AML.M0042 - Threat Intelligence Program](../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on coordinated AI service requests distributed across accounts, providers, and intermediary services. Use this intelligence to correlate activity across access pathways, identify shared routing infrastructure, and coordinate detection and response to campaigns whose scale and common control may be obscured within individual accounts or services.

## Software implementations

- [AML.S0036 - CLIProxyAPI](../../../Software/Tools/AML.S0036%20-%20CLIProxyAPI.md) — [CLIProxyAPI](../../../Software/Tools/AML.S0036%20-%20CLIProxyAPI.md) centrally routes AI service requests across multiple configured upstream accounts using round-robin load balancing. This distributes a client's workload across an account pool while presenting a common API endpoint to the client. [github](https://github.com/router-for-me/CLIProxyAPI)

## References

- [Detecting and preventing distillation attacks](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks)
- [China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0140)
