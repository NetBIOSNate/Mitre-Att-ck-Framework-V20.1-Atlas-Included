# AML.T0006 - Active Scanning

[MITRE ATLAS](../../../README.md) / [AML.TA0002 - Reconnaissance](../README.md)

Adversaries may actively scan for publicly reachable AI systems and resources for targeting. They may identify resources or systems that are misconfigured or are known vulnerable versions. This is distinct from other reconnaissance techniques that do not involve direct interaction with the victim system.

Since AI systems are often deployed in cloud environments, adversaries can use various enumeration methods to effectively discover AI systems and uncover information about their supporting underlying platforms. For agentic and SaaS-hosted systems, the victim system can include the shared platform and provider control plane on which the victim's agents are deployed.

Adversaries may probe the victim system to gather information and metadata for targeting, or actively scan for specific open ports on a potential victim's network or accessible deployed servers, with the goal of locating different types of deployed AI services. These methods could also include directly scanning a target's assets for publicly available AI agents, or for accessible agentic chat interfaces on SaaS platforms (ex: [Copilot Studio Hunter](https://github.com/mbrg/power-pwn/wiki/Modules:-Copilot-Studio-Hunter-%E2%80%90-Enum)).

Information gained from Active Scanning may yield targets that provide opportunities for other forms of reconnaissance such as [Search Open Technical Databases](../AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md), [Search Open Websites/Domains](../AML.T0095%20-%20Search%20Open%20Websites%20-%20Domains/README.md), [Search Open AI Vulnerability Analysis](../AML.T0001%20-%20Search%20Open%20AI%20Vulnerability%20Analysis/README.md), or [Gather RAG-Indexed Targets](../AML.T0064%20-%20Gather%20RAG-Indexed%20Targets/README.md).

**Tactics**  [AML.TA0002 - Reconnaissance](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1595](../../../../Enterprise/Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/README.md) · [MITRE ATT&CK T1595](https://attack.mitre.org/techniques/T1595/)

## Sub-techniques

- [AML.T0006.000 - Enumerate Hosted AI Resources](AML.T0006.000%20-%20Enumerate%20Hosted%20AI%20Resources/README.md)
- [AML.T0006.003 - Probe AI Agent Trigger Channels](AML.T0006.003%20-%20Probe%20AI%20Agent%20Trigger%20Channels/README.md)
- [AML.T0006.001 - Query Platform Metadata APIs](AML.T0006.001%20-%20Query%20Platform%20Metadata%20APIs/README.md)
- [AML.T0006.002 - Scan for Exposed AI Infrastructure](AML.T0006.002%20-%20Scan%20for%20Exposed%20AI%20Infrastructure/README.md)

## Case studies

- [AML.CS0023 - ShadowRay: Hijacking Exposed Ray Clusters](../../../Case%20Studies/Incidents/AML.CS0023%20-%20ShadowRay%20-%20Hijacking%20Exposed%20Ray%20Clusters.md) · [S00](../../../Case%20Studies/Incidents/AML.CS0023%20-%20ShadowRay%20-%20Hijacking%20Exposed%20Ray%20Clusters.md#step-s00)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s00)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S09](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s09)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S10](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s10), [S16](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s16)
- [AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md#step-s05)
- [AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md) · [S22](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s22)

## Mitigations

- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Require authenticated access to production AI endpoints and monitor queries to limit unauthenticated probing of exposed AI services.
- [AML.M0032 - Segmentation of AI Agent Components](../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Segment AI agent components so an exposed service does not reveal or provide reachability to additional internal components.
- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — By capturing adversarial fingerprinting behavior, honeypots can help provide early warning of sweeping activity meant to discover exposed AI targets and attack surfaces being explored by adversaries.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0006)
