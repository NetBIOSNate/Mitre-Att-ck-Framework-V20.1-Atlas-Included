# AML.T0143 - LLM Prompt Propagation

[MITRE ATLAS](../../../README.md) / [AML.TA0015 - Lateral Movement](../README.md)

Adversaries may cause malicious instructions already introduced into an AI-enabled environment to be transferred onward to additional storage locations, agents, applications, or resources where they can influence subsequent AI activity. This extends the attack beyond its initial point of introduction and may allow adversaries to influence additional targets without directly delivering a malicious prompt payload to each one.

Propagation may occur through email or other communications, shared documents, source-code repositories, persistent agent memory, retrieval systems, databases, shared workspaces, or direct agent-to-agent communication. Connected tools and services may also carry malicious instructions between otherwise separate environments. The transfer may result from an induced agent action or from copying, forwarding, synchronization, or other workflows that distribute affected content.

**Tactics**  [AML.TA0015 - Lateral Movement](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S10](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s10)
- [AML.CS0041 - Rules File Backdoor: Supply Chain Attack on AI Coding Assistants](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md#step-s05)
- [AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md) · [S12](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s12)

## Mitigations

- [AML.M0026 - Manage AI Agent Service Access](../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Limit messaging, publishing, and shared-resource write permissions to approved workflows and destinations. Separate distribution capabilities from unrelated service access to restrict where an adversary can propagate malicious instructions through the agent.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Limit delegated messaging, publishing, and shared-resource write permissions to destinations and resources required for the user's task. Withhold unnecessary distribution capabilities to restrict propagation of malicious instructions through the agent.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Authorize messaging, publishing, repository writes, shared-storage updates, and agent communication against task-permitted resources and destinations. Preserve restrictions through downstream services to prevent shared tool privileges from enabling propagation of malicious instructions beyond the caller's authorized scope.
- [AML.M0030 - Restrict AI Agent Tool Invocation on Untrusted Data](../../../Mitigations/AML.M0030%20-%20Restrict%20AI%20Agent%20Tool%20Invocation%20on%20Untrusted%20Data.md) — Restrict tool actions that send messages, publish content, modify shared resources, or communicate with other agents when untrusted content has entered the agent's context. Apply these restrictions to delayed actions and derived content that retain the influence of the untrusted instructions.
- [AML.M0032 - Segmentation of AI Agent Components](../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Isolate agent identities, storage, memory, messaging, and tool access, and mediate exchanges between agents and connected resources. Restrict cross-agent, cross-user, and cross-environment communication paths to limit where malicious instructions can be transferred after an initial compromise.
- [AML.M0033 - Input and Output Validation for AI Agent Components](../../../Mitigations/AML.M0033%20-%20Input%20and%20Output%20Validation%20for%20AI%20Agent%20Components.md) — Validate content before it is forwarded, published, synchronized, or written to resources used by other AI components. Inspect messages, shared documents, agent instructions, rules files, and templates for embedded malicious instructions, including hidden or encoded content. Perform validation outside the agent and at receiving boundaries before accepting transferred content.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0143)
