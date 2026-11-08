# AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Aim Security researchers discovered EchoLeak, a zero-click vulnerability in Microsoft 365 Copilot that could allow an attacker to exfiltrate sensitive enterprise data without user interaction.

The attack used a prompt injection delivered via an email sent to a target user. When M365 Copilot retrieved the email as part of its retrieval-augmented generation (RAG) context, the malicious instructions caused Copilot to search the user's accessible Microsoft 365 data and include sensitive information in its response context. The sensitive information was then exfiltrated via requests to attacker-controlled URLs without requiring the victim to open the email or click a link.

The attack chain bypassed multiple protections, including prompt injection defenses, link redaction, and content security policy restrictions.

Microsoft assigned the issue CVE-2025-32711 [cve-2025-32711](https://www.cve.org/CVERecord?id=CVE-2025-32711). It has since been remediated with no evidence it was exploited in the wild.

**Type**  Exercise

**Target**  Microsoft 365 Copilot

**Activity period**  2025-05

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers crafted malicious instructions designed to evade Microsoft's indirect prompt injection classifier, appear like ordinary business content, suppress attribution to the attacker-controlled email, and cause Copilot to include sensitive data in rendered output.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0066 - Retrieval Content Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0066%20-%20Retrieval%20Content%20Crafting/README.md)

The researchers embedded the prompt injection in business-like email content that was likely to be retrieved during a later Copilot interaction. The content was designed to appear relevant to ordinary enterprise workflows while carrying hidden instructions.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

The researchers staged an attacker-controlled web endpoint to receive outbound requests containing encoded sensitive data. The endpoint served as the collection point for the exfiltration channel.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researchers sent the email to a Microsoft 365 user inbox.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0068 - LLM Prompt Obfuscation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)

The prompt was phrased as benign business text rather than and obviously malicious prompt to evade user suspicion.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0070 - RAG Poisoning](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0070%20-%20RAG%20Poisoning/README.md)

The email was automatically ingested into a RAG database available to Copilot's retrieval pipeline.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.002 - Triggered](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.002%20-%20Triggered/README.md)

When the user later invoked Copilot, it retrieved the malicious email into its context and triggering the prompt injection.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.000 - RAG Databases](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md)

The malicious instructions caused Copilot to access sensitive enterprise information available through the user's Microsoft 365 account, such as emails, files, or project details.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0067 - LLM Trusted Output Components Manipulation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0067%20-%20LLM%20Trusted%20Output%20Components%20Manipulation/README.md)

The output was manipulated to avoid obvious attribution and to use reference-style Markdown links or images that bypassed link redaction.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0077 - LLM Response Rendering](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0077%20-%20LLM%20Response%20Rendering/README.md)

Copilot rendered a Markdown image whose URL encoded sensitive information. The client automatically attempted to fetch the image, creating a zero-click exfiltration path.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

To bypass CSP restrictions, the researchers routed the rendered image request through an allowed Microsoft Teams preview or proxy path, which fetched the attacker-controlled URL containing the encoded secret.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048 - External Harms](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/README.md)

If exploited against a real enterprise user, the attack could disclose confidential business data and harm the organization or affected users.

**Next**  End of path

## Attributed to

- [AML.E0016 - Cato Networks](../../Entities/AML.E0016%20-%20Cato%20Networks.md) (Security Evaluation)

## References

- [EchoLeak: The First Real-World Zero-Click Prompt Injection Exploit in a Production LLM System](https://arxiv.org/abs/2509.10540)
- [CVE-2025-32711](https://www.cve.org/CVERecord?id=CVE-2025-32711)
- [Breaking down 'EchoLeak', the First Zero-Click AI Vulnerability Enabling Data Exfiltration from Microsoft 365 Copilot](https://www.catonetworks.com/blog/breaking-down-echoleak/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0059)
