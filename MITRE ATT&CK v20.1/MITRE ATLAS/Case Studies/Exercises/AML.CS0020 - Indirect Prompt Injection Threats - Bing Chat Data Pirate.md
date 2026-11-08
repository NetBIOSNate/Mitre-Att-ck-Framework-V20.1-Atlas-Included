# AML.CS0020 - Indirect Prompt Injection Threats: Bing Chat Data Pirate

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Whenever interacting with Microsoft's new Bing Chat LLM Chatbot, a user can allow Bing Chat permission to view and access currently open websites throughout the chat session. Researchers demonstrated the ability for an attacker to plant an injection in a website the user is visiting, which silently turns Bing Chat into a Social Engineer who seeks out and exfiltrates personal information. The user doesn't have to ask about the website or do anything except interact with Bing Chat while the website is opened in the browser in order for this attack to be executed.

In the provided demonstration, a user opened a prepared malicious website containing an indirect prompt injection attack (could also be on a social media site) in Edge. The website includes a prompt which is read by Bing and changes its behavior to access user information, which in turn can sent to an attacker.

**Type**  Exercise

**Target**  Microsoft Bing Chat

**Activity period**  2023

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017 - Develop Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/README.md)

The attacker created a website containing malicious system prompts for the LLM to ingest in order to influence the model's behavior. These prompts are ingested by the model when access to it is requested by the user.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0068 - LLM Prompt Obfuscation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)

The malicious prompts were obfuscated by setting the font size to 0, making it harder to detect by a human.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

Bing chat is capable of seeing currently opened websites if allowed by the user. If the user has the adversary's website open, the malicious prompt will be executed.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0052.000 - Spearphishing via Social Engineering LLM](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/AML.T0052.000%20-%20Spearphishing%20via%20Social%20Engineering%20LLM/README.md)

The malicious prompt directs Bing Chat to change its conversational style to that of a pirate, and its behavior to subtly convince the user to provide PII (e.g. their name) and encourage the user to click on a link that has the user's PII encoded into the URL.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

With this user information, the attacker could now use the user's PII it has received for further identity-level attacks, such identity theft or fraud.

**Next**  End of path

## References

- [Indirect Prompt Injection Threats: Bing Chat Data Pirate](https://greshake.github.io/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0020)
