# AML.CS0056 - Model Distillation Campaigns Targeting Anthropic Claude

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Anthropic uncovered campaigns to extract Claude's capabilities carried out by the three Chinese AI Labs: DeepSeek, Moonshot, and MiniMax. Collectively, these campaigns used approximately 24,000 accounts and 16 million queries. They used model distillation to train their own models on the outputs of Claude in an attempt to replicate Claude's capabilities such as agentic reasoning, code generation, tool use, and computer use.

The labs obtained access through commercial proxy services that circumvented Anthropic policy on commercial access to Claude in China. Anthropic described proxy networks that distributed requests across accounts, its API, and third-party cloud platforms. These networks replaced banned accounts and mixed distillation requests with unrelated customer traffic, complicating detection of coordinated activity.

The following table summarizes the capabilities each lab targeted and the scale of their campaigns:
| Lab | Capabilities targeted for distillation | Reported scale |
|---|---|---|
| **DeepSeek** | Reasoning across multiple tasks, rubric-based evaluation, censorship-safe alternatives to politically sensitive queries | Over 150,000 exchanges |
| **Moonshot AI** | Reasoning and tool use, coding and data analysis, computer-use agent capabilities, computer vision | Over 3.4 million exchanges |
| **MiniMax** | Agentic coding, tool use, orchestration | Over 13 million exchanges |

Anthropic characterized these campaigns as illicit capability extraction that reduced the time and cost required to develop competing models. It also warned that models developed through illicit distillation could lack safeguards and enable downstream misuse, including offensive cyber operations, disinformation, and mass surveillance.

**Type**  Incident

**Target**  Anthropic Claude

**Activity period**  2026

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.005 - AI Service Proxies](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md)

DeepSeek, Moonshot AI, and MiniMax used commercial proxy services to gain access to Claude. This circumvented Anthropic's policy of not offering commercial access to Claude in China.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

DeepSeek, Moonshot AI, and MiniMax accessed Claude through approximately 24,000 fraudulent accounts collectively, including accounts supplied through commercial proxy networks. These accounts enabled authenticated requests to Claude through Anthropic API and third-party cloud platforms.

**Next**  [S03](#step-s03)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

DeepSeek, Moonshot AI, and MiniMax crafted large datasets of prompts designed to elicit responses with content that is useful in distilling capabilities from Claude.

**Next**  [S04](#step-s04)

### Step S03

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0140 - Centralized AI Service Request Routing](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md)

DeepSeek, Moonshot AI, and MiniMax used the commercial AI service proxies to distribute coordinated requests across accounts and access pathways to evade detection.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0024 - Exfiltration via AI Inference API](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0024%20-%20Exfiltration%20via%20AI%20Inference%20API/README.md)

DeepSeek, Moonshot AI, and MiniMax obtained Claude-generated responses through API access, including access mediated by commercial proxy services. The responses were transferred to the labs for use in their distillation campaigns.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0135 - Outputs from AI Models](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md)

DeepSeek, Moonshot AI, and MiniMax gathered Claude's responses as supervision for training their own models. Across the campaigns, Anthropic reported more than 16 million exchanges.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0005.001 - Replicate Behavior from Model Outputs](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md)

DeepSeek, Moonshot AI, and MiniMax used responses generated by Claude to train their own models and acquire selected Claude capabilities through distillation.

**Next**  [S09](#step-s09), [S08](#step-s08), [S07](#step-s07)

### Step S07

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.004 - AI Intellectual Property Theft](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md)

DeepSeek, Moonshot AI, and MiniMax acquired Claude capabilities via distillation at a fraction of the cost of developing their own models. They targeted the source model most differentiated capabilities, including agentic reasoning, tool use, and code generation.

**Next**  End of path

### Step S08

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.002 - Societal Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.002%20-%20Societal%20Harm/README.md)

Anthropic warned that models developed through illicit distillation could lack safeguards that restrict dangerous capabilities. Such models could support offensive cyber operations, disinformation campaigns, mass surveillance, or other activities that harm the public or vulnerable groups.

**Next**  End of path

### Step S09

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

Anthropic warned that models developed through illicit distillation were unlikely to retain the safeguards of the source model. Deployment of these models could expose individual users to harmful outputs or enable misuse against individuals.

**Next**  End of path

## Attributed to

- [AML.E0024 - DeepSeek](../../Entities/AML.E0024%20-%20DeepSeek.md) (Adversarial Operation)
- [AML.E0025 - Moonshot AI](../../Entities/AML.E0025%20-%20Moonshot%20AI.md) (Adversarial Operation)
- [AML.E0026 - MiniMax](../../Entities/AML.E0026%20-%20MiniMax.md) (Adversarial Operation)

## Reported by

- [AML.E0039 - Anthropic](../../Entities/AML.E0039%20-%20Anthropic.md)

## References

- [Detecting and preventing distillation attacks](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks)
- [AIID - Incident 1395: Anthropic Said DeepSeek, Moonshot, and MiniMax Used Fraudulent Accounts and Proxies to Illicitly Distill Claude Capabilities at Scale](https://incidentdatabase.ai/cite/1395/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0056)
