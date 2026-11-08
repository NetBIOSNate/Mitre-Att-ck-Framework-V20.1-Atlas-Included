# AML.T0029 - Denial of AI Service

[MITRE ATLAS](../../../README.md) / [AML.TA0011 - Impact](../README.md)

Adversaries may target AI-enabled systems with a flood of requests for the purpose of degrading or shutting down the service.
Since many AI systems require significant amounts of specialized compute, they are often expensive bottlenecks that can become overloaded.
Adversaries can intentionally craft inputs that require heavy amounts of useless compute from the AI system.

**Tactics**  [AML.TA0011 - Impact](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0016 - Achieving Code Execution in MathGPT via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md#step-s08)
- [AML.CS0036 - AIKatz: Attacking LLM Desktop Applications](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md) · [S11](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s11), [S12](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s12)

## Mitigations

- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit the number of queries users can perform in a given interval to prevent a denial of service.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Assess queries before inference call or enforce timeout policy for queries which consume excessive resources.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Access controls on model APIs can prevent an adversary from excessively querying and disabling the system.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Submit adversarial workloads and exercise dependency failures that could exhaust inference or supporting services. Apply quotas, concurrency limits, timeouts, resource isolation, and graceful degradation based on findings.
- [AML.M0036 - Limit AI Workload Resource Consumption](../../../Mitigations/AML.M0036%20-%20Limit%20AI%20Workload%20Resource%20Consumption.md) — Limit the resources consumed by individual requests to reduce denial of service from computationally expensive inputs.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0029)
