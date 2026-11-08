# AML.T0113 - Steal Web Session Cookie

[MITRE ATLAS](../../../README.md) / [AML.TA0013 - Credential Access](../README.md)

Adversaries may steal web application or service session cookies used to authenticate users to AI-enabled systems, AI services, or supporting enterprise applications.

Web applications often use session cookies as authentication tokens after a user has signed in. These cookies may remain valid for extended periods of time, even when the application is not actively being used. In AI systems, session cookies may provide access to chat interfaces, AI agents, AI service consoles, customer support platforms, model management dashboards, or other tools connected to sensitive data and workflows.

Adversaries may obtain session cookies from browser storage, process memory, network traffic, or applications that store authentication material in memory. They may also steal cookies by injecting malicious JavaScript into AI-rendered content, abusing unsafe rendering of LLM outputs, or tricking users or AI operators into opening poisoned content that executes in their browser.

In attacks on AI systems, session cookie theft can allow adversaries to bypass normal authentication flows and gain access to privileged AI-enabled applications without knowing the victim's username, password, or MFA secret. Stolen cookies may then be used with [Use Alternate Authentication Material: Web Session Cookie](../../12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0091%20-%20Use%20Alternate%20Authentication%20Material/AML.T0091.001%20-%20Web%20Session%20Cookie/README.md) to access the corresponding service as the victim.

**Tactics**  [AML.TA0013 - Credential Access](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Demonstrated

**ATT&CK mapping**  [Local ATT&CK T1539](../../../../Enterprise/Tactics/09%20TA0006%20-%20Credential%20Access/T1539%20-%20Steal%20Web%20Session%20Cookie/README.md) · [MITRE ATT&CK T1539](https://attack.mitre.org/techniques/T1539/)

## Case studies

- [AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md#step-s07)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0113)
