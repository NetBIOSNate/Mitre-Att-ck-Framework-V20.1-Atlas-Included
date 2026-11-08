# AML.T0078 - Drive-by Compromise

[MITRE ATLAS](../../../README.md) / [AML.TA0004 - Initial Access](../README.md)

Adversaries may gain access to an AI system through a user visiting a website over the normal course of browsing, or an AI agent retrieving information from the web on behalf of a user. Websites can contain an [LLM Prompt Injection](../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md) which, when executed, can change the behavior of the AI model.

The same approach may be used to deliver other types of malicious code that don't target AI directly (See [Drive-by Compromise in ATT&CK](https://attack.mitre.org/techniques/T1189/)).

**Tactics**  [AML.TA0004 - Initial Access](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Demonstrated

**ATT&CK mapping**  [Local ATT&CK T1189](../../../../Enterprise/Tactics/03%20TA0001%20-%20Initial%20Access/T1189%20-%20Drive-by%20Compromise/README.md) · [MITRE ATT&CK T1189](https://attack.mitre.org/techniques/T1189/)

## Case studies

- [AML.CS0021 - ChatGPT Conversation Exfiltration](../../../Case%20Studies/Exercises/AML.CS0021%20-%20ChatGPT%20Conversation%20Exfiltration.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0021%20-%20ChatGPT%20Conversation%20Exfiltration.md#step-s02)
- [AML.CS0045 - Data Exfiltration via an MCP Server used by Cursor](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md#step-s04)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s09)
- [AML.CS0055 - AI ClickFix: Hijacking Computer-Use Agents Using ClickFix](../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md#step-s03)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect web content before incorporating it into model context and validate actions induced by that content before execution. Block embedded instructions that redirect the agent into unauthorized activity. This addresses prompt-based compromise rather than exploitation of browser software vulnerabilities.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0078)
