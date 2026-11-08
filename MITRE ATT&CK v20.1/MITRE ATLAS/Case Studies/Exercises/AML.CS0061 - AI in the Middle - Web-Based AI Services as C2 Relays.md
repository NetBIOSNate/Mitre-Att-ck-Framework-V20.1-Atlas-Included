# AML.CS0061 - AI in the Middle: Web-Based AI Services as C2 Relays

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Check Point Research demonstrated an "AI in the Middle" attack in which malware can abuse web-based AI assistants with anonymous or unauthenticated browsing and URL-fetch capabilities as a covert command-and-control channel. The proof of concept used public AI web interfaces, including Grok and Microsoft Copilot, to cause the AI service to fetch attacker-controlled URLs, relay victim data in outbound requests, and return attacker-supplied commands through normal AI assistant responses.

Because the implant communicated with trusted AI service domains over ordinary HTTPS web traffic, the activity could blend into expected enterprise AI usage and evade controls focused on suspicious infrastructure, unusual protocols, API keys, service accounts, or revocable credentials. The lack of required authentication for some web-fetch workflows also made it harder for defenders to disable the channel by rotating API keys, suspending accounts, or revoking tokens. The researchers recommended stronger authentication and access controls for AI web-fetch features, along with improved visibility into AI-initiated network requests and AI assistant interactions.

**Type**  Exercise

**Target**  Enterprise machines with Grok and Microsoft Copilot access

**Activity period**  2026-02-17

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0095 - Search Open Websites/Domains](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0095%20-%20Search%20Open%20Websites%20-%20Domains/README.md)

The researchers evaluated public AI assistants with anonymous or unauthenticated web-browsing and URL-fetch behavior to identify services that could retrieve arbitrary adversary-controlled URLs without requiring API credentials. The researchers found Grok and Copilot met those conditions.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.002 - Domains](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.002%20-%20Domains/README.md)

The researchers registered a domain and deployed an HTTPS site to act as the relay endpoint.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

The researchers hosted benign-looking content while also returning data that the implant could treat as C2 instructions.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0047 - AI-Enabled Product or Service](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md)

Assuming prior access, the researchers used a custom C++ implant with an embedded browser or WebView component to interact with Grok or Microsoft Copilot through the public web interface rather than an API key.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers crafted prompts that instruct an AI service to fetch and summarize a website. The prompts caused victim data to be included in URL parameters, allowing the AI service's fetch request to relay data to the adversary-controlled server.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0068 - LLM Prompt Obfuscation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)

When some prompts were blocked by model safeguards, the researchers encoded or encrypted payload data into high-entropy blobs to reduce the chance that safeguards would identify the content as malicious.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0037 - Data from Local System](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0037%20-%20Data%20from%20Local%20System/README.md)

The implant collected basic host information from the local system. The researchers noted that this could be expanded to collect details such as username, domain, computer name, installed software, running processes, and startup programs.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0014 - Command and Control](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/README.md) / [AML.T0114 - AI Service Web Interface](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0114%20-%20AI%20Service%20Web%20Interface/README.md)

The implant initiated an anonymous web-based session with the public AI service and sent the crafted prompt. This formed a command-and-control channel whereby data was exfiltrated via requests to the adversary-controlled domain, and commands were communicated back via the response.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

The victim's collected host information was exfiltrated when the AI service followed the instructions to fetch the URL to the adversary-controlled domain with the data embedded in a query parameter.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0050 - Command and Scripting Interpreter](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0050%20-%20Command%20and%20Scripting%20Interpreter/README.md)

The AI service summarized the response from the adversary-controlled site, and the implant executed the extracted commands. In the proof of concept, the command launched Calculator using `cmd.exe /c calc.exe`; a real implant could execute other commands, download payloads, sleep, or collect additional data.

**Next**  End of path

## Attributed to

- [AML.E0030 - Check Point Research](../../Entities/AML.E0030%20-%20Check%20Point%20Research.md) (Security Evaluation)

## References

- [AI in the Middle: Turning Web-Based AI Services into C2 Proxies & The Future Of AI Driven Attacks](https://research.checkpoint.com/2026/ai-in-the-middle-turning-web-based-ai-services-into-c2-proxies-the-future-of-ai-driven-attacks/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0061)
