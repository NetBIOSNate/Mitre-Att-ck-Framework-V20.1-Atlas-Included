# AML.M0000 - Limit Public Release of Information

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Limit the public release of technical information about the AI stack used in an organization's products or services. Technical knowledge of how AI is used can be leveraged by adversaries to perform targeting and tailor attacks to the target system. Additionally, consider limiting the release of organizational information - including physical locations, researcher names, and department structures - from which technical details such as AI techniques, model architectures, or datasets may be inferred.

**Mitigation categories**  Policy

**Lifecycle phases**  Business and Data Understanding

## Techniques mitigated

- [AML.T0000 - Search Open Technical Databases](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md) — Limit the connection between publicly disclosed approaches and the data, models, and algorithms used in production.
- [AML.T0001 - Search Open AI Vulnerability Analysis](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0001%20-%20Search%20Open%20AI%20Vulnerability%20Analysis/README.md) — Limit disclosure of the production AI stack and system-specific technical details that let adversaries connect public vulnerability research to the deployed target.
- [AML.T0002 - Acquire Public AI Artifacts](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/README.md) — Limit the release of sensitive information in the metadata of deployed systems and publicly available applications.
- [AML.T0003 - Search Victim-Owned Websites](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0003%20-%20Search%20Victim-Owned%20Websites/README.md) — Restrict release of technical information on ML-enabled products and organizational information on the teams supporting ML-enabled products.
- [AML.T0004 - Search Application Repositories](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0004%20-%20Search%20Application%20Repositories/README.md) — Limit the release of sensitive information in the metadata of deployed systems and publicly available applications.
- [AML.T0005 - Replicate AI Model Behavior](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md) — Limiting release of technical information about a model and training data can reduce an adversary's ability to create an accurate proxy model.
- [AML.T0005.000 - Replicate Behavior from Gathered AI Artifacts](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.000%20-%20Replicate%20Behavior%20from%20Gathered%20AI%20Artifacts/README.md) — Limiting release of technical information about a model and training data can reduce an adversary's ability to create an accurate proxy model.
- [AML.T0005.002 - Adapt Existing Model to Replicate Behavior](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.002%20-%20Adapt%20Existing%20Model%20to%20Replicate%20Behavior/README.md) — Limiting release of technical information about a model and training data can reduce an adversary's ability to create an accurate proxy model.
- [AML.T0064 - Gather RAG-Indexed Targets](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0064%20-%20Gather%20RAG-Indexed%20Targets/README.md) — Withhold public documentation that identifies RAG data sources, indexes, and retrieval architecture.
- [AML.T0069 - Discover LLM System Information](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/README.md) — Withhold public prompt templates, model configuration, and architecture details that could aid LLM reconnaissance.
- [AML.T0084 - Discover AI Agent Configuration](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/README.md) — Limit public disclosure of agent tools, services, configuration, and workflows.
- [AML.T0084.001 - Tool Definitions](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.001%20-%20Tool%20Definitions/README.md) — Avoid publicly documenting sensitive agent tool definitions and capabilities.
- [AML.T0084.002 - Activation Triggers](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.002%20-%20Activation%20Triggers/README.md) — Avoid publicly disclosing agent activation keywords, events, and workflows.
- [AML.T0084.003 - Call Chains](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.003%20-%20Call%20Chains/README.md) — Limit public disclosure of agent call chains and execution-sink details.
- [AML.T0095 - Search Open Websites/Domains](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0095%20-%20Search%20Open%20Websites%20-%20Domains/README.md) — Limit public technical and organizational information that reveals the AI stack, services, personnel, or other targeting details on websites and domains.
- [AML.T0116 - Autonomous Reconnaissance](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md) — Limit release of information to reduce content an autonomous agent can use for reconnaissance.
- [AML.T0122 - Exploitation of Remote Services](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0122%20-%20Exploitation%20of%20Remote%20Services/README.md) — Limit the release of sensitive information about an AI stack to restrict the amount of information that an adversary can use to develop and perform exploits against services in the stack.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0000)
