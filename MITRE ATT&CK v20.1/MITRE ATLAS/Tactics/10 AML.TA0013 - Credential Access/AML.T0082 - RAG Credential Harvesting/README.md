# AML.T0082 - RAG Credential Harvesting

[MITRE ATLAS](../../../README.md) / [AML.TA0013 - Credential Access](../README.md)

Adversaries may attempt to use their access to a large language model (LLM) on the victim's system to collect credentials. Credentials may be stored in internal documents which can inadvertently be ingested into a RAG database, where they can ultimately be retrieved by an AI agent.

**Tactics**  [AML.TA0013 - Credential Access](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0035 - Data Exfiltration from Slack AI via Indirect Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md#step-s06)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Detect credentials and secrets in retrieved documents before they enter model context or are returned to a user. Redact or block prohibited disclosures and inspect resulting outputs and tool arguments for credential leakage.
- [AML.M0026 - Manage AI Agent Service Access](../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Limit retrieval identities to repositories, collections, and documents required by approved workflows, and separate roles across user groups or tenants. These restrictions reduce the sources from which an adversary can retrieve credentials through the agent.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Limit delegated retrieval access to repositories, collections, and documents required for the user's task to reduce potential credential sources. Avoid broadly privileged shared credentials and update effective access when the user's permissions change.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0082)
