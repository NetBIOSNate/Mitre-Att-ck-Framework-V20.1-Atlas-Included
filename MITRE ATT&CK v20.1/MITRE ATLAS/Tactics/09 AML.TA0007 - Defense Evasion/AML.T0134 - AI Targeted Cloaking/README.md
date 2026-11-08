# AML.T0134 - AI Targeted Cloaking

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may selectively deliver malicious or manipulated content to AI systems, while presenting different benign content to human users, web crawlers, or security detection mechanisms. They may identify AI browsers or agents via user-agent strings and condition the server response so that AI-based clients receive prompt injections or misleading content.

Preventing human visitors, conventional web crawlers, and security tools from observing the same content allows adversaries to make malicious input more difficult to detect. [AI Targeted Cloaking](README.md) may be combined with [Drive-by Compromise](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0078%20-%20Drive-by%20Compromise/README.md) to deliver an [LLM Prompt Injection](../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md).

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0134)
