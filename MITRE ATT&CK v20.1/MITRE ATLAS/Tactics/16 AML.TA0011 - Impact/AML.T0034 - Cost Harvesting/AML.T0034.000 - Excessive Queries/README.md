# AML.T0034.000 - Excessive Queries

[MITRE ATLAS](../../../../README.md) / [AML.TA0011 - Impact](../../README.md) / [AML.T0034 - Cost Harvesting](../README.md)

Adversaries may send an excessive number of otherwise normal or low-complexity queries to an AI system with the goal of overwhelming its capacity and increasing operating costs.

The attacker can automate high-volume request generation, exploiting rate limits, autoscaling policies, and pay-per-use billing models to drive sustained resource consumption without relying on specially crafted, computationally expensive inputs. This behavior can also lead to increased latency, request queuing, and service degradation or unavailability for legitimate users, as the system struggles to process the inflated traffic.

**Tactics**  [AML.TA0011 - Impact](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Generate controlled high-volume query activity. Verify authentication, user and tenant quotas, rate limits, anomaly detection, cost alerts, and service protection.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0034.000)
