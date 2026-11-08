# AML.T0034 - Cost Harvesting

[MITRE ATLAS](../../../README.md) / [AML.TA0011 - Impact](../README.md)

Adversaries may deliberately drive a victim's AI services beyond normal operating capacity with the intent of increasing the cost of services. This may be achieved via high-volume, low-complexity queries ([Excessive Queries](AML.T0034.000%20-%20Excessive%20Queries/README.md)) or low-volume, high-complexity queries ([Resource-Intensive Queries](AML.T0034.001%20-%20Resource-Intensive%20Queries/README.md)). In Generative AI or Agentic AI systems, adversarial prompts may be introduced into the model's context to cause ([Agentic Resource Consumption](AML.T0034.002%20-%20Agentic%20Resource%20Consumption/README.md)).

Unlike resource hijacking, where adversaries may leverage AI resources such as computational, memory, or storage for their own purposes, cost harvesting focuses on resource-centric pressure to a service to ultimately cause financial harm to the victim.

Cost Harvesting is especially relevant for cloud-hosted, pay-per-use AI/ML platforms (e.g., LLM APIs, generative image services, vision-language pipelines). By manipulating request volume or request complexity, an attacker can:
- Inflate the victim's compute or storage consumption, leading to higher operational costs.
- Trigger autoscaling mechanisms that provision additional resources, further amplifying cost and exposure.
- Saturate internal queues or GPU/TPU pipelines, causing latency spikes, request throttling, or outright service unavailability for legitimate users.

**Tactics**  [AML.TA0011 - Impact](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Sub-techniques

- [AML.T0034.002 - Agentic Resource Consumption](AML.T0034.002%20-%20Agentic%20Resource%20Consumption/README.md)
- [AML.T0034.000 - Excessive Queries](AML.T0034.000%20-%20Excessive%20Queries/README.md)
- [AML.T0034.001 - Resource-Intensive Queries](AML.T0034.001%20-%20Resource-Intensive%20Queries/README.md)

## Mitigations

- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit the number of queries users can perform in a given interval to hinder an attacker's ability to send computationally expensive inputs
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Access controls can limit API access and prevent cost harvesting.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Exercise requests and workflows designed to amplify inference, infrastructure, or external-service costs. Verify budgets, quotas, rate limits, workload controls, alerting, and termination mechanisms.
- [AML.M0036 - Limit AI Workload Resource Consumption](../../../Mitigations/AML.M0036%20-%20Limit%20AI%20Workload%20Resource%20Consumption.md) — Apply resource budgets to AI requests and workflows to limit costs from resource-intensive queries, excessive output, and uncontrolled agentic activity.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0034)
