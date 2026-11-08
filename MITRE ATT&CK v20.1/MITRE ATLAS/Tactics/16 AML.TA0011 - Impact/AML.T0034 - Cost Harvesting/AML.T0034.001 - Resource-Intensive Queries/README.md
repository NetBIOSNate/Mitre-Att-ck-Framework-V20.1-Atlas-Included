# AML.T0034.001 - Resource-Intensive Queries

[MITRE ATLAS](../../../../README.md) / [AML.TA0011 - Impact](../../README.md) / [AML.T0034 - Cost Harvesting](../README.md)

Adversaries may craft inputs specifically designed to increase the compute resources required for processing.

For generative AI models, adversaries may use long input sequences, requests for extremely long outputs, or prompts that require complex reasoning as strategies for increasing compute costs  [genai](https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/). For vision and language models, "sponge examples"  [arxiv](https://arxiv.org/abs/2006.03463) can be used to maximize energy consumption and decision latency.
Utilizing fewer resource-intensive queries instead of simply flooding the model with excessive queries may be more difficult to detect and block or limit.

**Tactics**  [AML.TA0011 - Impact](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Submit controlled requests designed to consume disproportionate inference resources. Verify input constraints, timeouts, workload limits, resource isolation, and cost monitoring.
- [AML.M0036 - Limit AI Workload Resource Consumption](../../../../Mitigations/AML.M0036%20-%20Limit%20AI%20Workload%20Resource%20Consumption.md) — Bound input size, output size, execution time, memory, and compute consumed by resource-intensive queries.

## References

- [\[2006.03463\] Sponge Examples: Energy-Latency Attacks on Neural Networks](https://arxiv.org/abs/2006.03463)
- [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0034.001)
