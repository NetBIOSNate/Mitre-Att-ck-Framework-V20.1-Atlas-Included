# AML.T0112.000 - Local AI Agent

[MITRE ATLAS](../../../../README.md) / [AML.TA0011 - Impact](../../README.md) / [AML.T0112 - Machine Compromise](../README.md)

Adversaries may achieve full system compromise by abusing AI agents running locally on a host, such as computer-use agents or AI-driven browsers. These agents are designed to autonomously interact with the operating system, applications, and external services, often with broad permissions to execute commands, access files, manage credentials, and control user workflows.

If an adversary is able to take control of an AI agent's behavior, they effectively gain the same level of access as the agent. This can result in complete control over the machine, including executing arbitrary code, accessing or exfiltrating sensitive data, modifying system configurations, and establishing persistence.

**Tactics**  [AML.TA0011 - Impact](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S17](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s17)
- [AML.CS0052 - LLMSmith: RCE Vulnerabilities in LLM-Integrated Applications](../../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md) · [S11](../../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md#step-s11)
- [AML.CS0055 - AI ClickFix: Hijacking Computer-Use Agents Using ClickFix](../../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md#step-s07)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Mediate local agent actions involving command execution, file access, credentials, and system configuration. Validate requested operations against authorized scope and block prohibited actions before they reach the operating system or connected applications.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Monitor local agent commands, file and credential access, tool use, and system changes.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0112.000)
