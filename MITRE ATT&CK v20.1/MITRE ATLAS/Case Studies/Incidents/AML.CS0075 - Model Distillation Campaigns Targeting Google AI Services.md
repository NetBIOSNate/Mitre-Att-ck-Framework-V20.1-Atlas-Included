# AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Google Threat Intelligence Group and Google DeepMind reported recurring distillation campaigns targeting Google AI services. Adversaries sought model outputs to reproduce capabilities, including reasoning, visual and audio understanding, image generation, and video generation.

The unknown actors utilized proxy infrastructure to orchestrate requests, distributing queries across thousands of compromised and fraudulent accounts spanning different product channels. Google reported that this fragmented activity obscured the attackers' origin and helped bypass security controls. [google-sep](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai/) The actors queried Google's services to elicit responses and collected the outputs. Model outputs are subsequently used by the actors to train or fine-tune their own models.

In February 2026, Google reported a campaign involving over 100,000 prompts that attempted to obtain Gemini's full reasoning traces rather than the summaries normally delivered to users. [google-feb](https://cloud.google.com/blog/topics/threat-intelligence/distillation-experimentation-integration-ai-adversarial-use) By September 2026, Google reported regularly observing coordinated distillation campaigns, some exceeding 100 million prompts. These campaigns targeted reasoning as well as multimodal capabilities, including visual and audio understanding, image generation, and video generation. [google-sep](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai/)

Google reported recognizing the reasoning-focused attack in real time and reducing its risk while protecting internal reasoning traces. For the broader campaigns, Google reported measures to reduce their utility and block responsible accounts, as well as techniques to identify Gemini-distilled models and trace their provenance. [google-feb](https://cloud.google.com/blog/topics/threat-intelligence/distillation-experimentation-integration-ai-adversarial-use) [google-sep](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai/)

**Type**  Incident

**Actor**  Multiple unknown actors

**Target**  Google AI Services, including Gemini

**Reporter**  Google Threat Intelligence Group, Google DeepMind

**Activity period**  2025 to 2026

## Procedure steps

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0139 - Compromise Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0139%20-%20Compromise%20Accounts/README.md)

Unknown actors compromised user credentials for Google AI services.

**Next**  [S03](#step-s03)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

Unknown actors established many fraudulent accounts for Google AI Services.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.005 - AI Service Proxies](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md)

Unknown actors deployed proxy infrastructure to orchestrate large-scale automated activity targeting Google AI models. The infrastructure supported requests distributed across credentials, accounts, and product channels.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

The fraudulent and compromised accounts were used to access Google AI services via the proxy infrastructure.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0140 - Centralized AI Service Request Routing](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md)

Unknown actors rotated queries across thousands of valid accounts across different product channels to obscure their origin and bypass security controls.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

Unknown actors crafted prompts to elicit outputs supporting capability replication.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0024 - Exfiltration via AI Inference API](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0024%20-%20Exfiltration%20via%20AI%20Inference%20API/README.md)

Unknown actors used the Google service inference APIs to acquire model outputs.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0135 - Outputs from AI Models](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md)

Unknown actors collected the model responses as training material for distillation.

Google identified over 100,000 prompts in the February 2026 reasoning-focused campaign. Later campaigns targeting reasoning and other capabilities exceeded 100 million prompts

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0005.001 - Replicate Behavior from Model Outputs](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md)

The distillation campaigns used outputs for training or fine-tuning models to reproduce selected Google model capabilities.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.004 - AI Intellectual Property Theft](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md)

The campaigns sought to appropriate proprietary capabilities from Google's models through distillation, reducing the effort and expense required to develop comparable capabilities independently.

**Next**  End of path

## References

- [GTIG AI Threat Tracker: Distillation, Experimentation, and (Continued) Integration of AI for Adversarial Use](https://cloud.google.com/blog/topics/threat-intelligence/distillation-experimentation-integration-ai-adversarial-use)
- [GTIG AI Threat Tracker: From Prompting to Autonomy - The Evolution of Adversarial AI](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0075)
