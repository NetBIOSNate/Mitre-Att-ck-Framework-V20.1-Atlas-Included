# AML.T0108 - AI Agent

[MITRE ATLAS](../../../README.md) / [AML.TA0014 - Command and Control](../README.md)

Adversaries may abuse AI agents present on the victim's system for command and control. AI agents are often granted access to tools that can execute shell commands, reach out to the internet, and interact with other services in the victim's environment, making them capable C2 agents.

The adversary may modify the behavior of an AI agent for C2 via [LLM Prompt Injection](../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md) and rely on the agent's ability to invoke tools to retrieve and execute the adversary's commands. They may maintain persistent control of an agent via [Modify AI Agent Configuration](../../07%20AML.TA0006%20-%20Persistence/AML.T0081%20-%20Modify%20AI%20Agent%20Configuration/README.md) or [AI Agent Context Poisoning](../../07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/README.md). They may instruct the agent to not report their actions to the user in an attempt to remain covert.

**Tactics**  [AML.TA0014 - Command and Control](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S16](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s16)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect agent inputs and proposed actions for attempts to establish unauthorized command retrieval, execution, or result transmission. Block tool operations and communications inconsistent with the agent's authorized task before execution.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Monitor agent prompts, decisions, tool use, and outputs for C2 behavior.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0108)
