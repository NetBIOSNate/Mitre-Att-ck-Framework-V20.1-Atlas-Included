# AML.M0032 - Segmentation of AI Agent Components

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Define enforceable security boundaries around AI agent tools, data sources, identities, and execution environments. Mediate access through authenticated APIs, isolate code execution via containers or virtual machines, restrict filesystem and network access, and limit tool invocation rates. Build execution environments from clean base images for each run, and do not carry forward any operational state. These controls limit the ability of untrusted processes or compromised components to affect the broader system.

When AI agents share infrastructure, isolate each agent's identity, credentials, state, storage, messaging, tools, and network access in order to prevent undesired agent-to-agent communication channels or coordination. Run the highest-risk workloads in network-isolated or air-gapped environments.

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Business and Data Understanding, Deployment

## Techniques mitigated

- [AML.T0006 - Active Scanning](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md) — Segment AI agent components so an exposed service does not reveal or provide reachability to additional internal components.
- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to perform unsafe actions that affect other components.
- [AML.T0085 - Data from AI Services](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/README.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to collect sensitive data from AI services.
- [AML.T0085.000 - RAG Databases](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to collect sensitive data from RAG databases.
- [AML.T0085.001 - AI Agent Tools](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to collect sensitive data.
- [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to compromise sensitive data sources.
- [AML.T0098 - AI Agent Tool Credential Harvesting](../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0098%20-%20AI%20Agent%20Tool%20Credential%20Harvesting/README.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to harvest credentials.
- [AML.T0118 - Autonomous AI Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/README.md) — Implement effective boundaries and sandboxing between system resources or services and agentic tools to limit undesired communication between agents.
- [AML.T0118.000 - Communication via Shared Artifacts](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md) — Implement effective boundaries and sandboxing between system resources or services and agentic tools to limit undesired communication between agents.
- [AML.T0118.001 - Direct Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md) — Implement effective boundaries and sandboxing between system resources or services and agentic tools to limit undesired communication between agents.
- [AML.T0121 - AI Agent Environment Reconstruction](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0121%20-%20AI%20Agent%20Environment%20Reconstruction/README.md) — Isolate runtime identities, credentials, storage, coordination resources, and network access. Restrict connectivity to provisioning services and alternative execution environments, and prevent replacement runtimes from automatically inheriting a terminated operation's access or state to limit unauthorized environment reconstruction.
- [AML.T0124 - Autonomous Attack Orchestration](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md) — Isolate agent identities, messaging, state, and execution environments. Restrict cross-agent assignment and coordination to explicitly authorized communication paths.
- [AML.T0143 - LLM Prompt Propagation](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md) — Isolate agent identities, storage, memory, messaging, and tool access, and mediate exchanges between agents and connected resources. Restrict cross-agent, cross-user, and cross-environment communication paths to limit where malicious instructions can be transferred after an initial compromise.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0032)
