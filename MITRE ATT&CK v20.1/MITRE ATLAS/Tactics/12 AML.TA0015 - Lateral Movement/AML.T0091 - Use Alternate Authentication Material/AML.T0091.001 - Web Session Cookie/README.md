# AML.T0091.001 - Web Session Cookie

[MITRE ATLAS](../../../../README.md) / [AML.TA0015 - Lateral Movement](../../README.md) / [AML.T0091 - Use Alternate Authentication Material](../README.md)

Adversaries may use stolen web session cookies to authenticate to AI-enabled applications and supporting services as another user. This technique may bypass some multi-factor authentication controls because the session represented by the cookie has already been authenticated.

Authentication cookies are commonly used by web applications and cloud-based services after a user has authenticated, allowing the user to continue using the service without repeatedly passing credentials. These cookies may remain valid for extended periods of time. After obtaining a cookie through [Steal Web Session Cookie](../../../10%20AML.TA0013%20-%20Credential%20Access/AML.T0113%20-%20Steal%20Web%20Session%20Cookie/README.md), an adversary may import the cookie into a browser or automated client they control and access the corresponding application as the victim while the session remains active.

In attacks on AI systems, web session cookies may grant access to AI chat histories, AI agent control panels, model provider dashboards, customer support systems, retrieval or knowledge management interfaces, or AI DevOps resources. If the stolen cookie belongs to an operator, support agent, developer, or administrator, the adversary may be able to view sensitive conversations, manipulate agent configuration, access private data available through AI tools, or perform actions with the victim account's permissions.

**Tactics**  [AML.TA0015 - Lateral Movement](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md)

**Maturity**  Demonstrated

**ATT&CK mapping**  [Local ATT&CK T1550.004](../../../../../Enterprise/Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.004%20-%20Web%20Session%20Cookie/README.md) · [MITRE ATT&CK T1550.004](https://attack.mitre.org/techniques/T1550/004)

## Case studies

- [AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot](../../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md) · [S09](../../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md#step-s09)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0091.001)
