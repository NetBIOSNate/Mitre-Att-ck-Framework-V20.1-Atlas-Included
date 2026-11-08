# AML.T0132 - Misconfigured or Publicly Exposed AI Services

[MITRE ATLAS](../../../README.md) / [AML.TA0004 - Initial Access](../README.md)

AI agents and LLM platforms are deployed across diverse architectures, including standalone servers, SaaS platforms, and low-code builders. All of these often have misconfigured access controls, ranging from missing authentication in LLM runtimes to permissive public access settings, that significantly expand their attack surface.

AI agent's security posture affects how attackers are able to explore which agentic attack surface is available to them and directly either expands or limits an adversary's ability to discover and interact with a target's AI agents. For example, one internet-facing AI service could be more easily discoverable by any unauthenticated user, while another may require compromised credentials to even be discovered.

Adversaries may discover and interact with AI agents and LLM services as unauthenticated users via a combination of various OSINT and active scanning methods. These could include using search engines to discover accessible agentic deployments (See [Search Open Technical Databases](../../01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)), search backlinks which could indicate existing or open agents which have been embedded to frontends (See [Search Open Websites/Domains](../../01%20AML.TA0002%20-%20Reconnaissance/AML.T0095%20-%20Search%20Open%20Websites%20-%20Domains/README.md)), or directly scanning a target's AI infrastructure (See [Active Scanning](../../01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md)).

**Tactics**  [AML.TA0004 - Initial Access](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0048 - Exposed ClawdBot Control Interfaces Leads to Credential Access and Execution](../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md#step-s01)

## Mitigations

- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Honeypots can safely absorb real attacks and exploit attempts, turning payloads into mapped defensive signatures for a potential target without risking real assets.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0132)
