# AML.CS0029 - Google Bard Conversation Exfiltration

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

[Embrace the Red](https://embracethered.com/blog/) demonstrated that Bard users' conversations could be exfiltrated via an indirect prompt injection. To execute the attack, a threat actor shares a Google Doc containing the prompt with the target user who then interacts with the document via Bard to inadvertently execute the prompt. The prompt causes Bard to respond with the markdown for an image, whose URL has the user's conversation secretly embedded. Bard renders the image for the user, creating an automatic request to an adversary-controlled script and exfiltrating the user's conversation. The request is not blocked by Google's Content Security Policy (CSP), because the script is hosted as a Google Apps Script with a Google-owned domain.

Note: Google has fixed this vulnerability. The CSP remains the same, and Bard can still render images for the user, so there may be some filtering of data embedded in URLs.

**Type**  Exercise

**Target**  Google Bard

**Activity period**  2023-11-23

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researcher developed a prompt that causes Bard to include a Markdown element for an image with the user's conversation embedded in the URL as part of its responses.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008 - Acquire Infrastructure](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/README.md)

The researcher identified that Google Apps Scripts can be invoked via a URL on `script.google.com` or `googleusercontent.com` and can be configured to not require authentication. This allows a script to be invoked without triggering Bard's Content Security Policy.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017 - Develop Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/README.md)

The researcher wrote a Google Apps Script that logs all query parameters to a Google Doc.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researcher shares a Google Doc containing the malicious prompt with the target user. This exploits the fact that Bard Extensions allow Bard to access a user's documents.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

When the user makes a query that results in the document being retrieved, the embedded prompt is executed. The malicious prompt causes Bard to respond with markdown for an image whose URL points to the researcher's Google App Script with the user's conversation in a query parameter.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0077 - LLM Response Rendering](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0077%20-%20LLM%20Response%20Rendering/README.md)

Bard automatically renders the markdown, which sends the request to the Google App Script, exfiltrating the user's conversation. This is allowed by Bard's Content Security Policy because the URL is hosted on a Google-owned domain.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

The user's conversation is exfiltrated, violating their privacy, and possibly enabling further targeted attacks.

**Next**  End of path

## Attributed to

- [AML.E0007 - Embrace the Red](../../Entities/AML.E0007%20-%20Embrace%20the%20Red.md) (Security Evaluation)

## References

- [Hacking Google Bard - From Prompt Injection to Data Exfiltration](https://embracethered.com/blog/posts/2023/google-bard-data-exfiltration/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0029)
