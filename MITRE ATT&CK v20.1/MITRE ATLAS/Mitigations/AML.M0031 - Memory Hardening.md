# AML.M0031 - Memory Hardening

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Memory Hardening protects persistent state used by AI agents, including saved preferences, episodic or semantic memories, conversation summaries, stored chat history, and agent-managed experience stores. Unlike guardrails that evaluate content during an interaction, memory hardening controls how durable agent state is created, modified, isolated, audited, and recovered.

Apply the following controls throughout the memory lifecycle, from creation and use through deletion and recovery:
- Enforce memory access controls: Authenticate memory operations and authorize them within the appropriate user, tenant, agent, and session scope.
- Set strong memory security policies: Enforce limits on memory size and update frequency, validate memory integrity, and define retention and deletion policies.
- Preserve memory provenance: Record the source of all memory updates and preserve a history with known good versions. Quarantine or roll-back suspicious records.
- Audit and monitor memory operations: Audit security relevant reads and writes. Monitor for unusual update frequency and repeated self-authored updates.

Content filtering and protections against malicious prompts may be provided by [Generative AI Guardrails](AML.M0020%20-%20Generative%20AI%20Guardrails.md), but does not replace memory access control, isolation, provenance, integrity, or recovery.

Open-source tools that implement memory hardening controls include OWASP Agent Memory Guard [owasp-agent-memory-guard-project](https://owasp.org/www-project-agent-memory-guard/) and Microsoft Agent Governance Toolkit [microsoft-agent-governance-toolkit](https://github.com/microsoft/agent-governance-toolkit). Memory management and persistence tooling such as Mem0 [mem0-entity-partitioning](https://docs.mem0.ai/cookbooks/essentials/entity-partitioning-playbook), and LangGraph Persistence [langgraph-persistence](https://docs.langchain.com/oss/python/langgraph/persistence) can also support aspects of memory hardening.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  AI Model Engineering, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0080 - AI Agent Context Poisoning](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/README.md) — Memory hardening reduces persistent context poisoning by controlling what an agent may save as memory, preventing saved data from becoming higher-authority instructions, and enabling poisoned records to be identified, quarantined, and rolled back.
- [AML.T0080.000 - Memory](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.000%20-%20Memory/README.md) — Memory hardening reduces persistent context poisoning by controlling what an agent may save as memory, preventing saved data from becoming higher-authority instructions, and enabling poisoned records to be identified, quarantined, and rolled back.

## References

- [OWASP Agent Memory Guard](https://owasp.org/www-project-agent-memory-guard/)
- [Microsoft Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit)
- [Mem0 Partition Memories by Entity](https://docs.mem0.ai/cookbooks/essentials/entity-partitioning-playbook)
- [LangGraph Persistence](https://docs.langchain.com/oss/python/langgraph/persistence)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0031)
