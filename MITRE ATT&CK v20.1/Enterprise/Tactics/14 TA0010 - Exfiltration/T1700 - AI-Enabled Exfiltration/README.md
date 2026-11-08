# T1700 - AI-Enabled Exfiltration

[Enterprise](../../../README.md) / [Exfiltration](../README.md)

Adversaries may utilize [Direct Prompt Injection](https://attack.mitre.org/techniques/T1699), [Indirect Prompt Injection](https://attack.mitre.org/techniques/T1698) or other methods to instruct enterprise AI agents to exfiltrate data.(Citation: Prompt-Injection Exfil)(Citation: Anthropic Report Sep 2026) When enterprise systems incorporate the use of AI assistants or other AI agents, adversaries may abuse these systems to weaponize sanctioned tools available to the agent.(Citation: Google Security State of Prompt Injections) 

As an AI agent processes queries or ingests data, an injected prompt can cause the agent to use its tool connections in unauthorized or unintended ways. When AI agents are induced to exfiltrate data, other exfiltration techniques likely apply as well to transfer the information out of the network, such as [Exfiltration to Code Repository](https://attack.mitre.org/techniques/T1567/001) or [Exfiltration Over Web Service](https://attack.mitre.org/techniques/T1567).(Citation: Google Cloud AI Risk Sep 2026)(Citation: Barracuda Prompt Injection Phishing Emails)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1700)

**Tactics**  [Exfiltration](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [SaaS](../../../Platforms/SaaS.md)

## Detection strategies

- [DET0927 - Detect AI-Enabled Exfiltration](../../../Defenses/Detection%20Strategies/DET0927%20-%20Detect%20AI-Enabled%20Exfiltration.md)

## Mitigations

- [M1048 - Application Isolation and Sandboxing](../../../Defenses/Mitigations/M1048%20-%20Application%20Isolation%20and%20Sandboxing.md) — Ensuring that LLM/AI systems are contained to only within the organizational network with no outside access can contain the exfiltration of sensitive data to within an organizational network.
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict file permissions to limit the exposure of sensitive data from AI agents.
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Employ user training to include the implications of AI agent use within corporate environments

## Sources

- [Anthropic Report Sep 2026](https://www.anthropic.com/threat-intelligence-report-september-2026)
- [Google Cloud AI Risk Sep 2026](https://cloud.google.com/security/resources/ai-risk-and-resilience-2026)
- [Barracuda Prompt Injection Phishing Emails](https://blog.barracuda.com/2026/10/07/email-attacks-target-both-humans-ai-assistants)
- [Prompt-Injection Exfil](https://arxiv.org/html/2608.27092)
- [Google Security State of Prompt Injections](https://blog.google/security/prompt-injections-web/)
