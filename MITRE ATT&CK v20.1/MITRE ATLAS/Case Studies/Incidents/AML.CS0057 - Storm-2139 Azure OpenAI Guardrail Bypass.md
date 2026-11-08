# AML.CS0057 - Storm-2139 Azure OpenAI Guardrail Bypass

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Storm-2139 built custom jailbreak tooling to bypass guardrails on Azure OpenAI Services, allowing users to generate harmful synthetic content.

Microsoft reported that members of Storm-2139 scraped exposed customer credentials from public sources and used them to access accounts for generative AI services. The group developed and operated tools and services that bypassed safety safeguards, modified service capabilities, and enabled end users to generate harmful and illicit content, including non-consensual intimate images of celebrities and other sexually explicit content.

The operation included creators who developed illicit tools, providers who modified and supplied those tools, and users who generated prohibited content. Microsoft pursued civil legal action.

**Type**  Incident

**Target**  Microsoft Azure OpenAI Service

**Reporter**  Microsoft

**Activity period**  2024-07 to 2024-12

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017 - Develop Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/README.md)

Storm-2139 creators developed a tool called de3u to facilitate unauthorized use of generative AI services and bypass safeguards.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008 - Acquire Infrastructure](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/README.md)

Storm-2139 acquired infrastructure to support a service that sold access to the jailbroken Azure OpenAI Service.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

Storm-2139 staged and operated a reverse proxy service to allow other malicious users to interact with abused generative AI services.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

Storm-2139 used exposed customer credentials scraped from public sources to access valid accounts for generative AI services.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0040 - AI Model Inference API Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md)

The stolen credentials provided access Azure OpenAI Service, allowing the actors and their customers to submit prompts and generate content. Storm-2139's de3u tool was used as the frontend for this access.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0054 - LLM Jailbreak](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0054%20-%20LLM%20Jailbreak/README.md)

Storm-2139 deliberately bypassed Azure OpenAI Service safeguards and content filters to generate prohibited outputs. Microsoft reported that the actors iterated on blocked prompts, substituted celebrity descriptions, and used altered wording or technical notation to evade filters.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0088 - Generate Deepfakes](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md)

End users generated abusive synthetic imagery, including non-consensual intimate images of celebrities and other sexually explicit, misogynistic, violent, or hateful content.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.002 - Societal Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.002%20-%20Societal%20Harm/README.md)

The generated abusive imagery could cause direct harm to depicted individuals.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.000 - Financial Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.000%20-%20Financial%20Harm/README.md)

Users whose accounts were stolen were harmed financially.

**Next**  End of path

## Attributed to

- [AML.E0027 - Storm-2139](../../Entities/AML.E0027%20-%20Storm-2139.md) (Adversarial Operation)

## References

- [Taking legal action to protect the public from abusive AI-generated content](https://blogs.microsoft.com/on-the-issues/2025/01/10/taking-legal-action-to-protect-the-public-from-abusive-ai-generated-content/)
- [Disrupting a global cybercrime network abusing generative AI](https://blogs.microsoft.com/on-the-issues/2025/02/27/disrupting-cybercrime-abusing-gen-ai/)
- [How Microsoft is taking down AI hackers who create harmful images of celebrities and others](https://news.microsoft.com/source/features/ai/how-microsoft-is-taking-down-ai-hackers-who-create-harmful-images-of-celebrities-and-others/)
- [AIID - Incident 955: Global Cybercrime Network Storm-2139 Allegedly Exploits AI to Generate Deepfake Content](https://incidentdatabase.ai/cite/955/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0057)
