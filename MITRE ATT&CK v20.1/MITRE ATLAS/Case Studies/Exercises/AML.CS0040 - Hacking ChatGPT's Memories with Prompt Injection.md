# AML.CS0040 - Hacking ChatGPT's Memories with Prompt Injection

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

[Embrace the Red](https://embracethered.com/blog/) demonstrated that ChatGPT's memory feature is vulnerable to manipulation via prompt injections. To execute the attack, the researcher hid a prompt injection in a shared Google Doc. When a user references the document, its contents is placed into ChatGPT's context via the Connected App feature, and the prompt is executed, poisoning the memory with false facts. The researcher demonstrated that these injected memories persist across chat sessions. Additionally, since the prompt injection payload is introduced through shared resources, this leaves others vulnerable to the same attack and maintains persistence on the system.

**Type**  Exercise

**Target**  OpenAI ChatGPT

**Activity period**  2024-02

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researcher crafted a basic prompt asking to set the memory context with a bulleted list of incorrect facts.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0068 - LLM Prompt Obfuscation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)

The researcher placed the prompt in a Google Doc hidden in the header with tiny font matching the document's background color to make it invisible.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The Google Doc was shared with the victim, making it accessible to ChatGPT's via its Connected App feature.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

When a user referenced something in the shared document, its contents was added to the chat context, and the prompt was executed by ChatGPT.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0080.000 - Memory](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.000%20-%20Memory/README.md)

The prompt caused new memories to be introduced, changing the behavior of ChatGPT. The chat window indicated that the memory has been set, despite the lack of human verification or intervention. All future chat sessions will use the poisoned memory store.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The memory poisoning prompt injection persists in the shared Google Doc, where it can spread to other users and chat sessions, making it difficult to trace sources of the memories and remove.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

The victim can be misinformed, misled, or influenced as directed by ChatGPT's poisoned memories.

**Next**  End of path

## Attributed to

- [AML.E0007 - Embrace the Red](../../Entities/AML.E0007%20-%20Embrace%20the%20Red.md) (Security Evaluation)

## References

- [ChatGPT: Hacking Memories with Prompt Injection](https://embracethered.com/blog/posts/2024/chatgpt-hacking-memories/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0040)
