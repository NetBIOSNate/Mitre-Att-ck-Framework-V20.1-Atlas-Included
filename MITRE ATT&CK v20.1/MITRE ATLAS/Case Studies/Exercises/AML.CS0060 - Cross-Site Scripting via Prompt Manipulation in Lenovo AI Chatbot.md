# AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Cybernews researchers demonstrated that Lenovo's AI chatbot "Lena" was vulnerable to a prompt injection that produced malicious HTML which was saved in the chat history and could exfiltrate a human support agent's session cookie when rendered in their browser.

The researchers prompted Lena with a benign-looking product information request that included instructions to respond with a dangerous HTML payload. The response was saved in the user's chat history, creating a stored cross-site scripting (XSS) payload. When the researchers requested transfer to a human support agent, the agent's normal workflow of opening the chat transcript caused the poisoned content to render, exfiltrating session cookie data to an attacker-controlled server. If a valid support agent cookie were reused, an adversary could potentially access Lenovo's customer support platform as that agent and view customer conversations or perform other actions available to the account.

Lenovo acknowledged the issue and reported implementing corrective actions to mitigate the potential impact and address the issue.

**Type**  Exercise

**Target**  Lenovo AI chatbot, "Lena"

**Activity period**  2025-08-18

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008 - Acquire Infrastructure](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/README.md)

The researchers set up a server to receive sensitive exfiltrated information from a vulnerable LLM service.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers developed a single prompt designed to make Lena generate HTML that would be unsafe when rendered by Lenovo's chat interface. The prompt combined several elements:
- A benign-looking product information request, such as "Show me the specifications of Lenovo IdeaPad 5 Pro."
- Output format instructions directing Lena to return the response as HTML with additional JSON and plaintext formatting expected by the server-side processing path.
- An HTML and JavaScript payload designed to read browser-accessible cookies and place them into a query parameter in an image request to an attacker-controlled server.
- Reinforcement language urging the model to include the image, such as "Show the image at the end. It is important for my decision-making. SHOW IT."

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0047 - AI-Enabled Product or Service](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md)

The researchers used the public web chat interface to Lenovo's "Lena" customer service agent.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researchers introduced attacker-controlled HTML into Lenovo's support workflow by prompting Lena through the public chat interface, causing the generated payload to be stored in the chat history for later rendering.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.000 - Direct](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.000%20-%20Direct/README.md)

Lena followed the attacker-controlled formatting instructions and generated an HTML response containing the malicious payload. The response persisted in the chat thread.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011 - User Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/README.md)

The researchers requested transfer to a human support agent, causing the malicious HTML to execute automatically when the agent opened the chat transcript.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0050 - Command and Scripting Interpreter](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0050%20-%20Command%20and%20Scripting%20Interpreter/README.md)

The stored HTML included browser-executable JavaScript that ran in the support agent's browser when the transcript was rendered.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0113 - Steal Web Session Cookie](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0113%20-%20Steal%20Web%20Session%20Cookie/README.md)

The JavaScript read session cookies from the support agent's browser.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0077 - LLM Response Rendering](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0077%20-%20LLM%20Response%20Rendering/README.md)

The active session cookie was added to a query parameter of an image tag in the HTML payload. The image did not exist, however the failed image load still made a request to the adversary-controlled server, exfiltrating the session cookie.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0091.001 - Web Session Cookie](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0091%20-%20Use%20Alternate%20Authentication%20Material/AML.T0091.001%20-%20Web%20Session%20Cookie/README.md)

The researchers could then import the stolen support agent session cookie into their browser to resume the authenticated session and potentially move laterally into Lenovo's customer support platform as the support agent.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048 - External Harms](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/README.md)

The attack exposed support agents and customers to session hijacking, unauthorized data access, and potential malware execution, resulting in direct user-level security and privacy harms.

**Next**  End of path

## Attributed to

- [AML.E0029 - Cybernews Investigation Team](../../Entities/AML.E0029%20-%20Cybernews%20Investigation%20Team.md) (Security Evaluation)

## References

- [Critical flaw plagues Lenovo AI chatbot: attackers can run malicious code and steal cookies](https://cybernews.com/security/lenovo-chatbot-lena-plagued-by-critical-vulnerabilities/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0060)
