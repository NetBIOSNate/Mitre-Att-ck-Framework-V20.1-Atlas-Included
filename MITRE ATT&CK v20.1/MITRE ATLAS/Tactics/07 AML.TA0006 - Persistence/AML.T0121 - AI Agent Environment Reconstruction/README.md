# AML.T0121 - AI Agent Environment Reconstruction

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

An autonomous AI agent may reconstruct the environment needed to continue an existing operation after its execution environment is lost, reset, replaced, denied, or made unusable. The agent may recover or recreate tools, dependencies, configuration, credentials or access paths, communication or coordination resources, working artifacts, and externally stored operational state in order to resume the same objective.

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S12](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s12)

## Mitigations

- [AML.M0026 - Manage AI Agent Service Access](../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Limit service permissions to provision execution environments, recreate supporting resources, and retrieve stored operational state to approved workflows. Separate identities and resource permissions across unrelated workflows or agent runs to restrict unauthorized environment reconstruction.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Limit delegated permissions to provision execution environments, recreate supporting resources, and retrieve stored operational state to those required for the user's task. Expire or revoke access when delegation ends to restrict unauthorized environment reconstruction.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Authorize tool requests to provision execution environments, recreate supporting resources, and retrieve stored operational state against task-permitted operations and resources. Preserve restrictions through downstream services to prevent broader tool privileges from enabling unauthorized environment reconstruction.
- [AML.M0032 - Segmentation of AI Agent Components](../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Isolate runtime identities, credentials, storage, coordination resources, and network access. Restrict connectivity to provisioning services and alternative execution environments, and prevent replacement runtimes from automatically inheriting a terminated operation's access or state to limit unauthorized environment reconstruction.
- [AML.M0037 - AI Agent Authority Expansion Controls](../../../Mitigations/AML.M0037%20-%20AI%20Agent%20Authority%20Expansion%20Controls.md) — Limit the ability of agents to autonomously acquire new credentials to prevent them from reconstructing environments on external services.
- [AML.M0043 - AI Agent External Resource Lifecycle Management](../../../Mitigations/AML.M0043%20-%20AI%20Agent%20External%20Resource%20Lifecycle%20Management.md) — Remove external operational state and revoke associated access to limit environment reconstruction and resumption of an operation.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0121)
