# AML.T0116 - Autonomous Reconnaissance

[MITRE ATLAS](../../../README.md) / [AML.TA0002 - Reconnaissance](../README.md)

Adversaries may use autonomous AI agents to conduct [Reconnaissance](../README.md) activities. Given an objective, target, or partial lead, an agent may autonomously determine what information to obtain and how to investigate it. It may interpret observations, identify gaps in its understanding of the externally observable attack surface, and select subsequent reconnaissance actions without a human specifying each investigative step.

The agent may formulate investigative questions or hypotheses, select sources and approaches for addressing them, and update its understanding as new information is obtained. Findings may generate additional reconnaissance objectives or change the scope, depth, or direction of the investigation. This creates a recursive action-observation process in which reconnaissance results influence what the agent investigates next rather than merely supplying output from a predefined procedure.

The agent may correlate information across public sources and externally accessible services, prioritize promising systems, investigate suspected vulnerabilities, abandon unsuccessful approaches, or select alternative methods. It may also expand or substitute targets based on discovered names, infrastructure, or contextual relationships and independently reassess whether a system remains relevant or in scope. Incorrect assumptions may cause unrelated or unauthorized systems to be pursued, while successful scope recognition may cause the agent to stop or redirect its activity.

Autonomous AI agents can sustain reconnaissance across long-running operations, reason over multiple information sources, and test many alternative paths at a speed and volume difficult for human operators to maintain.

**Tactics**  [AML.TA0002 - Reconnaissance](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s05), [S15](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s15)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S08](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s08)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S07](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s07), [S12](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s12)
- [AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md#step-s04)
- [AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s02), [S21](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s21)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s01)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Limit release of information to reduce content an autonomous agent can use for reconnaissance.
- [AML.M0001 - Limit Model Artifact Release](../../../Mitigations/AML.M0001%20-%20Limit%20Model%20Artifact%20Release.md) — Limit release of AI artifacts to reduce an autonomous agent's ability to conduct targeting.
- [AML.M0037 - AI Agent Authority Expansion Controls](../../../Mitigations/AML.M0037%20-%20AI%20Agent%20Authority%20Expansion%20Controls.md) — Treat newly discovered resources as outside the authorized boundary to prevent expansion of the agent's permitted interactions without approval.
- [AML.M0038 - AI Agent Scope Drift Detection](../../../Mitigations/AML.M0038%20-%20AI%20Agent%20Scope%20Drift%20Detection.md) — Identify when an agent attempts to discover or probe resources in ways no longer consistent with the authorized objective.
- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Deploy decoy assets or credentials to slow down or divert autonomous reconnaissance efforts. Detect adversary interactions with decoy assets or use of decoy credentials and block associated unauthorized access attempts.
- [AML.M0042 - Threat Intelligence Program](../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on autonomous reconnaissance campaigns, including targeting, infrastructure, and observed sequences of investigative actions. Use this intelligence to correlate related reconnaissance activity, identify assets receiving adversary attention, and prioritize monitoring and exposure reduction.

## Software implementations

- [AML.S0022 - Claude Code](../../../Software/Tools/AML.S0022%20-%20Claude%20Code.md) — Within GTG-1002's intrusion framework, [Claude Code](../../../Software/Tools/AML.S0022%20-%20Claude%20Code.md) autonomously inspected target systems and infrastructure, identified valuable databases, and reported its findings to human operators.[[source-1]]
- [AML.S0025 - Hermes Agent](../../../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) — In knaithe's configuration, [Hermes Agent](../../../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) used DeepSeek and connected tools to enumerate internet-facing systems through FOFA, research public vulnerabilities and exploit repositories, and assess candidate targets. The agent selected subsequent investigative actions without further operator input recovered in the session. [source-1](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0116)
