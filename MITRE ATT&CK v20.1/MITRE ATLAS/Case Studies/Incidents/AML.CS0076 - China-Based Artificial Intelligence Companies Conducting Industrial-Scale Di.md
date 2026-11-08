# AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

NSA, CISA, and FBI attributed industrial-scale distillation campaigns to six China-based AI companies. Since at least late 2024, these companies collected outputs from U.S. AI models over millions of exchanges, and used the responses to train or improve their own models. The companies targeted specific capabilities, such as reasoning, coding, and agentic functionality, from different models to improve their own models and reduce development costs.

The companies obtained access through fraudulent accounts, bulk purchases of premium subscriptions, and gray-market AI service proxies known as "transfer stations." Centralized routing infrastructure distributed requests across provider APIs, cloud services, third-party aggregators, relays, and account pools. This infrastructure enabled operators to bypass geographic restrictions, manage quotas and costs, and switch access pathways when blocked. Distributing requests across providers and pathways also helped obscure the coordinated activity and evade detection.

The agencies reported prompts designed to elicit hidden chain-of-thought reasoning, including DeepSeek requests to reconstruct the reasoning behind completed responses. Operators also automatically removed organizational identifiers from requests to hinder attribution, collected model responses into training datasets, and used automated quality-assurance pipelines to detect degraded outputs and distinguish defensive countermeasures from ordinary service problems.

The advisory provides additional actor-specific reporting on the capabilities and models targeted:

| Actor | Reported activity period | Collection and distillation details |
| --- | --- | --- |
| [DeepSeek](../../Entities/AML.E0024%20-%20DeepSeek.md) | Since at least late 2024 | The agencies reported targeting Claude, GPT, Gemini, and Grok variants to support R1 and V3 development. Targeted functionality included reasoning, legal specialization, API rule-driven tasks, question answering, writing, supervised fine-tuning optimization, and agentic capabilities. |
| [Moonshot AI](../../Entities/AML.E0025%20-%20Moonshot%20AI.md) | Since at least mid-2025 | The agencies reported cross-provider collection targeting supervised fine-tuning, reinforcement learning, software engineering, and mathematics. The advisory specifically states that Claude Fable 5 data supported Kimi-K3 and GPT-4o data supported Kimi-K2. |
| [MiniMax](../../Entities/AML.E0026%20-%20MiniMax.md) | Late 2025 | The agencies reported using Claude and Gemini services to improve M2's reasoning, reinforcement learning, supervised fine-tuning, and software engineering capabilities. They also identified using GPT-5's code review, agentic functionality, and dataset refinement among the targeted capabilities. |
| [Alibaba](../../Entities/AML.E0040%20-%20Alibaba%20Group.md) | Late 2025 | The agencies reported distillation from Claude and GPT variants to improve Alibaba's models, including the Qwen family. Targets included software engineering, customer-service dialogue, image or virtual-character creation, evaluation and training datasets, and agentic workflows. |
| [StepFun](../../Entities/AML.E0041%20-%20StepFun.md) | Late 2025 to early 2026 | The agencies reported collecting outputs from Claude and GPT variants to improve Step 4's coding and agentic functions. |
| [Z.AI](../../Entities/AML.E0042%20-%20Z.AI.md) | By mid-2026 | The agencies reported distillation of chain-of-thought reasoning capabilities from GPT-5.5 and Claude Opus 4.8 involving billions of tokens. |

**Type**  Incident

**Target**  Models from Anthropic, OpenAI, Google, and XAI

**Reporter**  NSA, CISA, FBI

**Activity period**  2024 to ongoing

## Procedure steps

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

The companies created fraudulent accounts, including accounts that obscured their country of origin, and procured premium subscriptions in bulk to support access at scale.

**Next**  [S03](#step-s03)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.005 - AI Service Proxies](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md)

The companies used gray-market AI service proxies known as "transfer stations" to access U.S. models, bypass geographic restrictions, and obscure the origin of requests.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

The companies used established accounts and premium-subscription pools to access AI services.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0140 - Centralized AI Service Request Routing](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md)

The companies used centralized infrastructure to distribute requests across native APIs, cloud providers, third-party aggregators, and account pools to evade restrictions and avoid detection. Routing incorporated service-health monitoring, automated failover when blocked, centralized quota and budget management, and cost-aware pathway selection.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0141 - AI Service Request Metadata Sanitization](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0141%20-%20AI%20Service%20Request%20Metadata%20Sanitization/README.md)

The companies automatically removed organizational identifiers from requests to obscure their origin and hinder attribution.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0063 - Discover AI Model Outputs](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0063%20-%20Discover%20AI%20Model%20Outputs/README.md)

The companies identified model outputs useful for extracting selected capabilities and generating training data. They performed adaptive discovery intended to identify valuable extractable data, supporting targeted collection rather than indiscriminate gathering.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The companies crafted systematic sets of prompts to elicit outputs for distillation, concentrating queries on selected domains and capabilities.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.000 - Direct](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.000%20-%20Direct/README.md)

The companies submitted their adversarial prompts directly to target models to override intended behavior and elicit responses supporting their distillation objectives.

**Next**  [S09](#step-s09), [S10](#step-s10)

### Step S09

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0054 - LLM Jailbreak](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0054%20-%20LLM%20Jailbreak/README.md)

The companies used prompts designed to elicit hidden chain-of-thought reasoning despite restrictions on its disclosure. DeepSeek requested that models imagine and articulate the reasoning behind completed responses step by step.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0024 - Exfiltration via AI Inference API](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0024%20-%20Exfiltration%20via%20AI%20Inference%20API/README.md)

The companies queried U.S. AI services via their proxy infrastructure and obtained model responses for subsequent collection and training.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0135 - Outputs from AI Models](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md)

The companies systematically collected millions of responses into training datasets, concentrating queries on selected domains and capabilities.

**Next**  [S12](#step-s12)

### Step S12

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0042 - Verify Attack](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md)

The companies deployed automated quality-assurance pipelines with multimodal validation to detect degraded outputs and distinguish defensive data degradation from ordinary service problems. These checks assessed the quality and usefulness of acquired responses.

**Next**  [S13](#step-s13)

### Step S13

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0005.001 - Replicate Behavior from Model Outputs](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md)

The companies used outputs from U.S. models to train or improve their own models, targeting selected capabilities rather than necessarily reproducing complete models.

**Next**  [S14](#step-s14)

### Step S14

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.004 - AI Intellectual Property Theft](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md)

NSA, CISA, and FBI assessed that the campaigns appropriated proprietary functionality and capabilities, reduced development costs and timelines, and undermined providers' competitive advantages.

**Next**  End of path

## Attributed to

- [AML.E0024 - DeepSeek](../../Entities/AML.E0024%20-%20DeepSeek.md) (Adversarial Operation)
- [AML.E0025 - Moonshot AI](../../Entities/AML.E0025%20-%20Moonshot%20AI.md) (Adversarial Operation)
- [AML.E0026 - MiniMax](../../Entities/AML.E0026%20-%20MiniMax.md) (Adversarial Operation)
- [AML.E0040 - Alibaba Group](../../Entities/AML.E0040%20-%20Alibaba%20Group.md) (Adversarial Operation)
- [AML.E0041 - StepFun](../../Entities/AML.E0041%20-%20StepFun.md) (Adversarial Operation)
- [AML.E0042 - Z.AI](../../Entities/AML.E0042%20-%20Z.AI.md) (Adversarial Operation)

## References

- [China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0076)
