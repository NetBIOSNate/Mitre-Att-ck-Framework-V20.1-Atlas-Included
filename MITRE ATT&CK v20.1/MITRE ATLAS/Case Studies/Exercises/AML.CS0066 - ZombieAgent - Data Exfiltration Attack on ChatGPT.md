# AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

ZombieAgent is a proof-of-concept indirect prompt injection attack demonstrated by Radware against OpenAI's ChatGPT Deep Research and Connector functionality. The attacks showed how instructions concealed in externally controlled content, such as emails and documents, could be ingested and executed by ChatGPT during normal user activity. The demonstration used Gmail as the injection source, but any ChatGPT Connector such as Outlook, Google Drive, Jira, or Teams could be similarly abused.

The Radware Security Researchers sent a malicious email containing concealed instructions to a Gmail inbox connected to ChatGPT. When the user later asked ChatGPT to perform an ordinary inbox-related task, ChatGPT retrieved the email and executed its instructions. The user did not open, click, or knowingly interact with the malicious email.

The injected instructions caused ChatGPT to collect information from connected services and exfiltrate it through URL requests. OpenAI had introduced a control preventing ChatGPT from dynamically constructing or modifying URLs which could be used to exfiltrate data via query parameters. The researchers bypassed this control by supplying an indexed dictionary of preconstructed static URLs and instructing ChatGPT to open URLs corresponding to individual characters to exfiltrate the collected data.

The researchers also showed that the malicious instructions could manipulate ChatGPT's Memory. The injected memories instructed ChatGPT to retain sensitive information from future conversations and to retrieve and execute a designated attacker-controlled email during later interactions. This created a persistent mechanism for repeated collection and exfiltration across chat sessions.

The researchers also demonstrated how the malicious prompt could be propagated. A compromised agent could collect email addresses from the victim's mailbox and use its connected email capabilities to send additional messages containing the malicious prompt to those contacts. Recipients whose AI agents later processed the poisoned messages could become additional victims.

**Type**  Exercise

**Target**  OpenAI ChatGPT

**Activity period**  2025-09-25

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers crafted malicious prompt payloads for the different attack variants. The payloads contained instructions for connector access, data collection, static-URL encoding, memory manipulation, and propagation.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

The researchers prepared infrastructure to receive exfiltrated data.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0068 - LLM Prompt Obfuscation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)

The prompt injection was visually concealed in externally controlled content using techniques such as white-on-white text or microscopic font sizes. ChatGPT could process the instructions even though they were not apparent to the user.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researchers sent a malicious email to an inbox connected to ChatGPT or provided a malicious document that could be uploaded or retrieved through a connected service. This introduced the prompt into a data source accessible to the victim's agent.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

A later, legitimate user request, such as asking ChatGPT to summarize the inbox, caused the agent to retrieve the malicious content and execute the concealed instructions. The user did not knowingly interact with the malicious email.

**Next**  [S05](#step-s05), [S06](#step-s06)

### Step S05

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0080.000 - Memory](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.000%20-%20Memory/README.md)

The malicious instructions caused ChatGPT to create or modify memories. The poisoned memories instructed ChatGPT to retain sensitive information from conversations and to perform attacker-defined actions during later interactions.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The malicious instructions caused ChatGPT to invoke connector and web-access capabilities available under the victim's authority. This gave the prompt access to information and actions that were not directly available to the researchers.

**Next**  [S07](#step-s07), [S11](#step-s11)

### Step S07

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.001 - AI Agent Tools](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md)

ChatGPT used connected-service tools to retrieve information accessible to the victim's agent. Demonstrated collection included mailbox content and email contact information.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0054 - LLM Jailbreak](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0054%20-%20LLM%20Jailbreak/README.md)

The researchers bypassed ChatGPT's restriction against dynamically constructing or modifying URLs by supplying an indexed dictionary of static URLs. ChatGPT encoded collected data by selecting and opening the URL corresponding to each character and position.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

ChatGPT invoked its URL-opening capability to request the selected adversary-controlled URLs. The researchers reconstructed the sensitive data from the character and position encoded in the resulting server requests. The requests originated from OpenAI's infrastructure rather than the victim's endpoint or corporate network.

**Next**  End of path

### Step S11

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.001 - AI Agent Tools](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md)

ChatGPT searched the victim's mailbox and collected email addresses belonging to potential additional targets.

**Next**  [S12](#step-s12)

### Step S12

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0143 - LLM Prompt Propagation](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md)

The malicious instructions caused ChatGPT to reproduce the prompt in new emails or documents and distribute them to collected contacts. If another AI agent processed the poisoned content, the attack could propagate between users or connected AI systems.

**Next**  End of path

## Attributed to

- [AML.E0035 - Radware](../../Entities/AML.E0035%20-%20Radware.md) (Security Evaluation)

## References

- [ZombieAgent: New ChatGPT Vulnerabilities Let Data Theft Continue (and Spread)](https://www.radware.com/blog/threat-intelligence/zombieagent/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0066)
