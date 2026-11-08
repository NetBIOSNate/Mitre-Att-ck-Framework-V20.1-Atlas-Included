# AML.T0117 - Autonomous Attack-Path Adaptation

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Adversaries may use an AI agent to autonomously construct and repeatedly revise an attack path toward an adversary-defined objective. Given a high-level objective, the system may derive intermediate objectives, identify prerequisites, and compare candidate paths, and incorporate observations from previous actions to adaptively sequence techniques without a human directing each step.

Autonomous AI agents may also exhibit this behavior while pursuing an objective provided for a legitimate, benign, or authorized purpose when the intermediate objectives or methods selected by the system cross an authorization, trust, control, or safety boundary and result in attempted or realized harmful cyber activity.

Through repeated observation-decision-action cycles, the system may interpret command output, errors, defensive responses, changes in access, and newly discovered information. It may use those observations to reprioritize actions, replace an intermediate objective, abandon an unproductive branch, discard findings invalidated by additional evidence, or pursue an alternative path.

An autonomous AI system may generate enabling objectives whose primary purpose is to increase its future operational capability rather than directly accomplishing the assigned objective. These objectives may include acquiring new exploits (See [Autonomous Exploit Development](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.001%20-%20Autonomous%20Exploit%20Development/README.md)), additional authorities, identities, execution environments, communication paths, tools, or trust relationships that expand the set of actions available to subsequent planning cycles. Newly acquired capabilities may themselves become prerequisites for additional enabling objectives, resulting in progressive expansion of the agent's operational reach over the course of an operation.

Attack-path replanning may occur within one agent run or emerge across multiple independent agents. Agents may communicate persistent, shared artifacts (See [Autonomous AI Agent Communication: Communication via Shared Artifacts](../AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md)), allowing discoveries, requests, capabilities, constraints, task state, and results produced by one agent to affect the subsequent path selected by another. Participating agents may adopt peer requests, divide work voluntarily, reuse successful methods, continue incomplete activity, or redirect their local paths without a centralized planner, shared context window, or complete view of the broader operation.

Human involvement does not preclude autonomous attack-path replanning. A human operator, user, evaluator, or workflow may select the target, define the objective, establish constraints, provide capabilities, or approve consequential transitions.

[Autonomous Attack-Path Adaptation](README.md) and [Autonomous Attack Orchestration](../AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md) may occur together but describe different control functions. Attack-path adaptation captures how evidence changes the selected path. Attack orchestration captures how work is allocated, coordinated, validated, and redirected across agents.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S00](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s00)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S07](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s07)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s05)
- [AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md#step-s02)
- [AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s01), [S10](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s10), [S20](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s20)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S00](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s00)

## Mitigations

- [AML.M0037 - AI Agent Authority Expansion Controls](../../../Mitigations/AML.M0037%20-%20AI%20Agent%20Authority%20Expansion%20Controls.md) — Constrain actions that seek new authorities, identities, execution environments, tools, communication paths, or trust relationships.
- [AML.M0038 - AI Agent Scope Drift Detection](../../../Mitigations/AML.M0038%20-%20AI%20Agent%20Scope%20Drift%20Detection.md) — Evaluate whether dynamically generated intermediate actions are within the agent's task scope.
- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Decoy assets, such as honeypots, can slow down autonomous operations by obscuring real attack paths, and can provide an early warning to the defender about adversarial autonomous activity.
- [AML.M0042 - Threat Intelligence Program](../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on observed autonomous cyber behaviors, including observed changes in objectives and techniques following failed attempts, defensive responses, or newly acquired access. Use this intelligence to identify alternative attack paths requiring protection, update defensive evaluations, and prepare response procedures for continued activity after an initial path is blocked.

## Software implementations

- [AML.S0022 - Claude Code](../../../Software/Tools/AML.S0022%20-%20Claude%20Code.md) — Within GTG-1002's intrusion framework, [Claude Code](../../../Software/Tools/AML.S0022%20-%20Claude%20Code.md) selected and revised intermediate attack actions based on observed results, progressing through vulnerability testing, exploitation, and credential-based access while human operators retained critical decisions. [anthropic-report](https://www.anthropic.com/news/disrupting-AI-espionage)
- [AML.S0025 - Hermes Agent](../../../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) — After determining that Langflow targets lacked exploitation prerequisites, the DeepSeek-powered [Hermes Agent](../../../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) researched vulnerabilities across ten product families and selected n8n as an alternative. It obtained a public exploit chain, assessed target configurations, and attempted further exploitation. The observed autonomous attempts did not obtain access. [source-1](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0117)
