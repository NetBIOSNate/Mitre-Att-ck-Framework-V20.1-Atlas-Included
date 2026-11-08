# AML.T0081 - Modify AI Agent Configuration

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may modify the configuration files for AI agents on a system. This allows malicious changes to persist beyond the life of a single agent and affects any agents that share the configuration.

Configuration changes may include modifications to the system prompt, tampering with or replacing knowledge sources, modification to settings of connected tools, and more. Through those changes, an attacker could redirect outputs or tools to malicious services, embed covert instructions that exfiltrate data, or weaken security controls that normally restrict agent behavior.

Adversaries may modify or disable a configuration setting related to security controls, such as those that would prevent the AI Agent from taking actions that may be harmful to the user's system without human-in-the-loop oversight. Disabling AI agent security features may allow adversaries to achieve their malicious goals and maintain long-term corruption of the AI agent.

**Tactics**  [AML.TA0006 - Persistence](../README.md), [AML.TA0007 - Defense Evasion](../../09%20AML.TA0007%20-%20Defense%20Evasion/README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0041 - Rules File Backdoor: Supply Chain Attack on AI Coding Assistants](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md#step-s04)
- [AML.CS0050 - OpenClaw 1-Click Remote Code Execution](../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md#step-s06)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S13](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s13)

## Mitigations

- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Exercise unauthorized changes to system prompts, tools, knowledge sources, security settings, and approval requirements. Improve access controls, change approval, integrity monitoring, and restoration from trusted configurations.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0081)
