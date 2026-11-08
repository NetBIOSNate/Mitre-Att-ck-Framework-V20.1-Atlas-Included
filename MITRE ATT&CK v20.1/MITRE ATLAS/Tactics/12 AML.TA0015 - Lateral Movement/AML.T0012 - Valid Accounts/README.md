# AML.T0012 - Valid Accounts

[MITRE ATLAS](../../../README.md) / [AML.TA0015 - Lateral Movement](../README.md)

Adversaries may obtain and abuse credentials of existing accounts as a means of gaining Initial Access.
Credentials may take the form of usernames and passwords of individual user accounts or API keys that provide access to various AI resources and services.

Compromised credentials may provide access to additional AI artifacts and allow the adversary to perform [Discover AI Artifacts](../../11%20AML.TA0008%20-%20Discovery/AML.T0007%20-%20Discover%20AI%20Artifacts/README.md).
Compromised credentials may also grant an adversary increased privileges such as write access to AI artifacts used during development or production.

**Tactics**  [AML.TA0004 - Initial Access](../../04%20AML.TA0004%20-%20Initial%20Access/README.md), [AML.TA0012 - Privilege Escalation](../../08%20AML.TA0012%20-%20Privilege%20Escalation/README.md), [AML.TA0015 - Lateral Movement](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1078](../../../../Enterprise/Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md) · [MITRE ATT&CK T1078](https://attack.mitre.org/techniques/T1078/)

## Case studies

- [AML.CS0010 - Microsoft Azure Service Disruption](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md#step-s01)
- [AML.CS0012 - Face Identification System Evasion via Physical Countermeasures](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md#step-s01)
- [AML.CS0018 - Arbitrary Code Execution with Google Colab](../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md#step-s02)
- [AML.CS0030 - LLMjacking: Stolen Cloud Credentials Used to Access Cloud LLM Services.](../../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md#step-s03)
- [AML.CS0035 - Data Exfiltration from Slack AI via Indirect Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md#step-s02)
- [AML.CS0036 - AIKatz: Attacking LLM Desktop Applications](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s00)
- [AML.CS0044 - LAMEHUG: Malware Leveraging Dynamic AI-Generated Commands](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md) · [S00](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md#step-s00)
- [AML.CS0050 - OpenClaw 1-Click Remote Code Execution](../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md#step-s05)
- [AML.CS0056 - Model Distillation Campaigns Targeting Anthropic Claude](../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md#step-s01)
- [AML.CS0057 - Storm-2139 Azure OpenAI Guardrail Bypass](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md#step-s03)
- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S17](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s17), [S33](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s33)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S15](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s15)
- [AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md) · [S07](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md#step-s07), [S08](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md#step-s08)
- [AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md) · [S17](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s17)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S32](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s32), [S38](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s38), [S41](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s41)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s04)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s03)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Restrict model registries and training data to approved identities so compromised accounts expose only explicitly authorized AI assets.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Authenticate production AI endpoints and monitor model queries for misuse of otherwise valid credentials.
- [AML.M0043 - AI Agent External Resource Lifecycle Management](../../../Mitigations/AML.M0043%20-%20AI%20Agent%20External%20Resource%20Lifecycle%20Management.md) — Revoke credentials and disable unneeded accounts to limit reuse of agent-associated access after its authorized purpose ends.

## Software implementations

- [AML.S0009 - OAI Reverse Proxy](../../../Software/Tools/AML.S0009%20-%20OAI%20Reverse%20Proxy.md) — [OAI Reverse Proxy](../../../Software/Tools/AML.S0009%20-%20OAI%20Reverse%20Proxy.md) forwards requests to AI services using configured account credentials while withholding those credentials from downstream users. During LLMjacking activity, requests bearing its user-agent attempted to access models with compromised cloud credentials. [llmjacking](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0012)
