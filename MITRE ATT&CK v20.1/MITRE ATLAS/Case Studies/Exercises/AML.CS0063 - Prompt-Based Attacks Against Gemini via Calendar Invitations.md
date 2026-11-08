# AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

SafeBreach researchers demonstrated how adversary-controlled instructions embedded in productivity content, including Google Calendar invitations, emails, and shared files, could influence the behavior of Gemini-powered assistants when that content was later retrieved.

An adversary places malicious instructions in content likely to be retrieved in response to a future victim request. When Gemini incorporates the adversary-controlled content into the conversation context, the instructions can influence the model's behavior and cause it to use the victim's authorized tools and connected services in unintended ways.

The demonstrated attack paths share a common chain: an adversary sends a poisoned Calendar invitation; the victim asks Gemini about upcoming events; Gemini retrieves the malicious event title and adds it to conversation context; and a later victim response (e.g. "Thanks") triggers the embedded instructions. The attack was demonstrated on both the Gemini web and Android applications. The web application could access Workspace services, while the Android application exposed additional device and connected-home capabilities. The same chain was shown to produce several impacts:

- Generate toxic content or adversary-selected promotions in Gemini responses.
- Delete or create Calendar events using the victim's authorized Calendar access.
- Control connected Google Home devices, including windows, boilers, and lights.
- Open an adversary-controlled website, initiating a download and exposing the victim's IP address for approximate geolocation.
- Invoke the Zoom application on the victim's device and stream video to an adversary-controlled meeting.
- Retrieve Calendar or Gmail data, encode it in an adversary-controlled URL, and transmit it through a browser request.

**Type**  Exercise

**Target**  Google Gemini

**Activity period**  2025-08-06 to 2026-10-28

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0006 - Active Scanning](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md)

The researchers directly probed Gemini interfaces to understand its agent selection and execution behavior.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0084 - Discover AI Agent Configuration](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/README.md)

The researchers identified available agents, tools, and connected services, including Calendar, Gmail, Google Home, Android Utilities, Chrome, and Zoom.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers crafted malicious instructions tailored to Gemini's retrieval behavior, agents, and available tool permissions.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researchers sent a poisoned Calendar invitation or email containing malicious instructions in its title or subject.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

When the victim asked Gemini to summarize Calendar events or emails, Gemini retrieved the adversary-controlled content and incorporated it into its context.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0080.001 - Thread](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.001%20-%20Thread/README.md)

The injected instructions remained in the conversation context, including Calendar content concealed behind 'Show more,' to influence subsequent turns.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0094 - Delay Execution of LLM Instructions](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0094%20-%20Delay%20Execution%20of%20LLM%20Instructions/README.md)

The malicious instructions deferred the action until a future victim interaction, avoiding restrictions imposed during the original retrieval turn.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.002 - Triggered](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.002%20-%20Triggered/README.md)

A later victim response such as "Thanks" activated the stored instructions.

**Next**  [S08](#step-s08), [S10](#step-s10), [S12](#step-s12), [S14](#step-s14), [S16](#step-s16), [S18](#step-s18)

### Step S08

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0054 - LLM Jailbreak](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0054%20-%20LLM%20Jailbreak/README.md)

The malicious prompt caused Gemini to follow roleplay and instruction-override content to replace its normal response with adversary-selected toxic content or promotions.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

Gemini delivered harmful content or repeated adversary-selected promotions to the victim.

**Next**  End of path

### Step S10

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The malicious prompt caused Gemini to invoke Google Calendar tools using the victim's authorized access to modify Calendar data.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0101 - Data Destruction via AI Agent Tool Invocation](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0101%20-%20Data%20Destruction%20via%20AI%20Agent%20Tool%20Invocation/README.md)

Gemini deleted a victim Calendar event.

**Next**  End of path

### Step S12

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The malicious prompt caused Gemini to invoke Google Home using the victim's authorized connection to control connected windows, a boiler, or lights.

**Next**  [S13](#step-s13)

### Step S13

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

The victim's physical environment was altered, potentially creating safety, privacy, property, or financial harm.

**Next**  End of path

### Step S14

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The malicious prompt caused Gemini to use Android Utilities to open an adversary-controlled URL in the victim's browser and initiate a download.

**Next**  [S15](#step-s15)

### Step S15

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

The adversary-controlled website received the victim device's source IP address, enabling approximate geolocation.

**Next**  End of path

### Step S16

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The malicious prompt caused Gemini to use Android Utilities and an application link or redirect chain to invoke Zoom.

**Next**  [S17](#step-s17)

### Step S17

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

Unauthorized video streaming caused privacy harm to the victim.

**Next**  End of path

### Step S18

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.001 - AI Agent Tools](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md)

The malicious prompt caused Gemini to retrieve Calendar event titles or Gmail email subjects using connected agent tools and place the contents into adversary-controlled URLs.

**Next**  [S19](#step-s19)

### Step S19

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

Gemini opened the constructed URL using Android Utilities, transmitting the victim's Calendar or email data to the adversary-controlled server.

**Next**  End of path

## Attributed to

- [AML.E0032 - SafeBreach Labs](../../Entities/AML.E0032%20-%20SafeBreach%20Labs.md) (Security Evaluation)

## References

- [Invitation Is All You Need: Hacking Gemini](https://www.safebreach.com/blog/invitation-is-all-you-need-hacking-gemini/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0063)
