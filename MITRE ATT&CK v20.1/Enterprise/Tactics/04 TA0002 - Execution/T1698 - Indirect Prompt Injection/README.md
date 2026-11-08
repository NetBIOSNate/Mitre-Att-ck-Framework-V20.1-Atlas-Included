# T1698 - Indirect Prompt Injection

[Enterprise](../../../README.md) / [Execution](../README.md)

Adversaries may deliver malicious prompts to an LLM indirectly by embedding the prompts in content that the adversary expects may be processed by an LLM.(Citation: NIST indirect prompt injection) These prompts can be included in web pages,(Citation: Palo Alto Indirect Prompt Injection ITW) documents, emails, tickets,(Citation: Snyk Indirect Prompt Injection) code, or other sources that an agent, copilot, or other AI system may retrieve and process. When an LLM processes this content, the embedded instructions may cause the system to perform unintended behaviors.(Citation: GTIG AI Threats Sep 2026) 

Adversaries may use indirect prompt injection to [Impair Autonomous Defenses](https://attack.mitre.org/techniques/T1685/007), and for unauthorized execution of any capabilities available to the LLM.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1698)

**Tactics**  [Execution](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [SaaS](../../../Platforms/SaaS.md)

## Mitigations

- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Prevent instructions contained in retrieved or externally supplied content from independently authorizing consequential agent actions. Require tool/API requests derived from external content to satisfy authorization and policy controls independent of the model-generated decision.
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Restrict network resources and external destinations accessible to AI agents that process untrusted content. Limit outbound communication and access to unrelated internal services to reduce exfiltration and lateral effects following successful injection.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Prevent AI agents processing untrusted or externally controlled content from automatically exercising privileged permissions. Require additional authorization for sensitive operations derived from retrieved content.
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict AI agents to files, directories, repositories, and content stores required for their approved workflows. Limit write access separately from read access where possible to reduce the actions available following successful indirect prompt injection.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Use dedicated identities for AI agents and restrict their permissions to the minimum resources and actions required by the approved workflow. Do not allow retrieved content to change the authorization context associated with the agent.
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users and administrators to treat content processed by AI agents as potentially adversarial and to require independent validation before approving sensitive actions proposed as a result of externally sourced content.

## Detection strategies

- [DET0942 - Retrieved Instruction with Unauthorized Agent Action](../../../Defenses/Detection%20Strategies/DET0942%20-%20Retrieved%20Instruction%20with%20Unauthorized%20Agent%20Action.md)

## Sources

- [Palo Alto Indirect Prompt Injection ITW](https://unit42.paloaltonetworks.com/ai-agent-prompt-injection/)
- [GTIG AI Threats Sep 2026](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai)
- [NIST indirect prompt injection](https://csrc.nist.gov/glossary/term/indirect_prompt_injection)
- [Snyk Indirect Prompt Injection](https://snyk.io/blog/cline-supply-chain-attack-prompt-injection-github-actions/)
