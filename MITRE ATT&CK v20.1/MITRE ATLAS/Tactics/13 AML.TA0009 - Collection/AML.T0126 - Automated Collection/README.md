# AML.T0126 - Automated Collection

[MITRE ATLAS](../../../README.md) / [AML.TA0009 - Collection](../README.md)

Adversaries may use automated techniques to collect data from AI systems and supporting enterprise environments. Automation may use scripts, command interpreters, command-line tools, or AI agent tools to identify, retrieve, copy, or aggregate data without a human selecting each individual item.

Collection criteria may be fixed, such as file name, type, location, owner, date. Automation may also collect repeatedly, monitor for new material, traverse related resources, or combine data from local systems, cloud services, repositories, databases, object stores, and application APIs.

In AI environments, targeted material may include models, datasets, configurations, conversation histories, retrieval databases, deployment information, logs, and other operational data.

**Tactics**  [AML.TA0009 - Collection](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1119](../../../../Enterprise/Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md) · [MITRE ATT&CK T1119](https://attack.mitre.org/techniques/T1119/)

## Case studies

- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S19](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s19)
- [AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md) · [S11](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md#step-s11)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Restrict access to model repositories, training data, and other AI resources to prevent or limit collection.
- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Deploy decoy files or resources and detect when they are accessed to expose automated collection workflows.

## Software implementations

- [AML.S0022 - Claude Code](../../../Software/Tools/AML.S0022%20-%20Claude%20Code.md) — Within GTG-1002's intrusion framework, [Claude Code](../../../Software/Tools/AML.S0022%20-%20Claude%20Code.md) automated the extraction of private data from compromised systems and categorized the collected information by intelligence value. [anthropic-report](https://www.anthropic.com/news/disrupting-AI-espionage)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0126)
