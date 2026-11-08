# AML.M0036 - Limit AI Workload Resource Consumption

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Limit the resources that an AI request, inference job, or agent workflow can consume. Set bounds on input size, batch size, execution time, memory, compute, and output size. Generative AI services should also limit context and output tokens. Agentic AI systems should limit iterations, retries, tool calls, parallel tasks, delegation depth, and downstream spending.

Apply resource limits across the complete workflow because one request may initiate multiple model calls or external actions. Use timeouts, cost ceilings, circuit breakers, and safe termination conditions to prevent individual workloads from exhausting shared resources. These controls complement query-rate limits, which address large numbers of otherwise inexpensive requests.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0029 - Denial of AI Service](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0029%20-%20Denial%20of%20AI%20Service/README.md) — Limit the resources consumed by individual requests to reduce denial of service from computationally expensive inputs.
- [AML.T0034 - Cost Harvesting](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0034%20-%20Cost%20Harvesting/README.md) — Apply resource budgets to AI requests and workflows to limit costs from resource-intensive queries, excessive output, and uncontrolled agentic activity.
- [AML.T0034.001 - Resource-Intensive Queries](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0034%20-%20Cost%20Harvesting/AML.T0034.001%20-%20Resource-Intensive%20Queries/README.md) — Bound input size, output size, execution time, memory, and compute consumed by resource-intensive queries.
- [AML.T0034.002 - Agentic Resource Consumption](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0034%20-%20Cost%20Harvesting/AML.T0034.002%20-%20Agentic%20Resource%20Consumption/README.md) — Limit agent iterations, tool calls, fan-out, runtime, and downstream spending to constrain agentic resource consumption.
- [AML.T0124 - Autonomous Attack Orchestration](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md) — Limit concurrent agents, parallel assignments, delegation depth, runtime, and aggregate resource consumption to constrain the scale and duration of orchestrated workflows.

## References

- [OWASP LLM10:2025 Unbounded Consumption](https://genai.owasp.org/llmrisk/llm102025-unbounded-consumption/)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0036)
