# T1699 - Direct Prompt Injection

[Enterprise](../../../README.md) / [Execution](../README.md)

Adversaries may input malicious prompts directly into an LLM’s user interface.(Citation: NIST Direct Prompt Injection) The prompts can be designed to bypass safeguards, manipulate context, override previous instructions, or coerce the LLM into unauthorized behavior.(Citation: OWASP Prompt Injection) 

Adversaries may use direct prompt injection to [Generate Content](https://attack.mitre.org/techniques/T1683) prohibited by the LLM's guardrails or to induce the system to utilize its capabilities in unintended or prohibited ways.(Citation: Gemini AI Misuse Jan 2025)(Citation: Palo Alto Prompt Injection) Adversaries may achieve this by instructing the LLM to ignore previous instructions or safety rules, or by impersonating a role such as a researcher or privileged user.(Citation: Cybersec Guru Prompt Injection)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1699)

**Tactics**  [Execution](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [SaaS](../../../Platforms/SaaS.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary abused Claude Code by utilizing a file-write operation within the prompt that created a `claude.md` file that contained a pre-written 1,084-line document containing penetration testing scripts that were used in the campaign.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [C0062 - Anthropic AI-orchestrated Campaign](../../../Threat%20Intelligence/Campaigns/C0062%20-%20Anthropic%20AI-orchestrated%20Campaign.md) — During the [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062), the adversary entered a prompt that claimed the user was an employee of a cybersecurity firm and that Claude was being used for defensive cybersecurity testing to authorize restricted operations.(Citation: Anthropic AI Orchestrated Campaign NOV 2025) [Anthropic AI Orchestrated Campaign NOV 2025](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf)

## Detection strategies

- [DET0941 - Instruction Override with Unauthorized AI Activity](../../../Defenses/Detection%20Strategies/DET0941%20-%20Instruction%20Override%20with%20Unauthorized%20AI%20Activity.md)

## Mitigations

- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Prevent user-supplied AI prompts from directly authorizing consequential actions. Enforce tool, API, command, and resource authorization outside the model and reject requested actions that exceed the permissions associated with the initiating user or agent task.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict access to privileged AI capabilities and require explicit authorization or human approval for AI-generated actions involving administrative functions, sensitive resources, or privileged tools.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Associate AI interactions with authenticated identities and constrain AI-mediated actions to the permissions of the initiating user. Do not allow prompt content to establish or elevate the authorization context used by downstream tools or services.
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users responsible for AI-enabled systems to recognize attempts to manipulate system instructions, role boundaries, or safety controls through user-provided prompts and to independently validate consequential AI-generated actions.

## Sources

- [Gemini AI Misuse Jan 2025](https://services.google.com/fh/files/misc/adversarial-misuse-generative-ai.pdf)
- [NIST Direct Prompt Injection](https://csrc.nist.gov/glossary/term/direct_prompt_injection)
- [OWASP Prompt Injection](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
- [Palo Alto Prompt Injection](https://www.paloaltonetworks.com/cyberpedia/what-is-a-prompt-injection-attack)
- [Cybersec Guru Prompt Injection](https://thecybersecguru.com/news/instagram-meta-ai-vulnerability-account-recovery-exploit/)
