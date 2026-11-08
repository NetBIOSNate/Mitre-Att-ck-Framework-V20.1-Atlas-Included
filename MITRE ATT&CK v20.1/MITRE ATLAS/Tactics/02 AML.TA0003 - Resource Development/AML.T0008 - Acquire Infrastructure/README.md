# AML.T0008 - Acquire Infrastructure

[MITRE ATLAS](../../../README.md) / [AML.TA0003 - Resource Development](../README.md)

Adversaries may buy, lease, or rent infrastructure for use throughout their operation.
A wide variety of infrastructure exists for hosting and orchestrating adversary operations.
Infrastructure solutions include physical or cloud servers, domains, mobile devices, and third-party web services.
Free resources may also be used, but they are typically limited.
Infrastructure can also include physical components such as countermeasures that degrade or disrupt AI components or sensors, including printed materials, wearables, or disguises.

Use of these infrastructure solutions allows an adversary to stage, launch, and execute an operation.
Solutions may help adversary operations blend in with traffic that is seen as normal, such as contact to third-party web services.
Depending on the implementation, adversaries may use infrastructure that makes it difficult to physically tie back to them as well as utilize infrastructure that can be rapidly provisioned, modified, and shut down.

**Tactics**  [AML.TA0003 - Resource Development](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1583](../../../../Enterprise/Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/README.md) · [MITRE ATT&CK T1583](https://attack.mitre.org/techniques/T1583/)

## Sub-techniques

- [AML.T0008.000 - AI Development Workspaces](AML.T0008.000%20-%20AI%20Development%20Workspaces/README.md)
- [AML.T0008.005 - AI Service Proxies](AML.T0008.005%20-%20AI%20Service%20Proxies/README.md)
- [AML.T0008.001 - Consumer Hardware](AML.T0008.001%20-%20Consumer%20Hardware/README.md)
- [AML.T0008.002 - Domains](AML.T0008.002%20-%20Domains/README.md)
- [AML.T0008.003 - Physical Countermeasures](AML.T0008.003%20-%20Physical%20Countermeasures/README.md)
- [AML.T0008.004 - Serverless](AML.T0008.004%20-%20Serverless/README.md)

## Case studies

- [AML.CS0029 - Google Bard Conversation Exfiltration](../../../Case%20Studies/Exercises/AML.CS0029%20-%20Google%20Bard%20Conversation%20Exfiltration.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0029%20-%20Google%20Bard%20Conversation%20Exfiltration.md#step-s01)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s06)
- [AML.CS0057 - Storm-2139 Azure OpenAI Guardrail Bypass](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md#step-s01)
- [AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md#step-s00)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s05)

## Mitigations

- [AML.M0043 - AI Agent External Resource Lifecycle Management](../../../Mitigations/AML.M0043%20-%20AI%20Agent%20External%20Resource%20Lifecycle%20Management.md) — Decommission agent-acquired infrastructure when authorization ends to limit its continued use beyond the authorized task.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0008)
