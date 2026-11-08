# AML.T0120 - AI Artifact Repository

[MITRE ATLAS](../../../README.md) / [AML.TA0014 - Command and Control](../README.md)

Adversaries may repurpose AI artifact repositories as asynchronous command-and-control channels. Commands, payloads, or tasking may be placed in repository objects for a compromised system to retrieve or poll. The compromised system may then write execution results, status, or collected information back to the repository for retrieval by the adversary.

This communication can use ordinary artifact and repository operations, such as reading or updating artifact content, metadata, or revisions through an API or version-control interface. The repository acts as a message queue or dead drop, allowing the parties to exchange information without a continuous direct connection and potentially blending the activity with legitimate artifact traffic.

**Tactics**  [AML.TA0014 - Command and Control](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S25](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s25)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Control access to AI assets at rest to prevent an adversary from repurposing these channels for command and control.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Monitor repository accesses and correlate them with known workflows. Investigate repeated polling, unexpected repositories, and writes from workloads that normally only download artifacts.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0120)
