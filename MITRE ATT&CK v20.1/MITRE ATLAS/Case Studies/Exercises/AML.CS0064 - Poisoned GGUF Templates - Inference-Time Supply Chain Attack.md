# AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers from Pillar Security and Fujitsu Research of Europe demonstrated an inference-time supply-chain backdoor in which poisoned chat templates alter model and agent behavior without modifying model weights. The backdoor is embedded in trusted prompt-construction logic, allowing it to remain dormant until triggered and evade defenses that inspect only external prompt content.

The researchers demonstrated the attack using GPT-Generated Unified Format (GGUF), a widely used model format that packages quantized weights, configuration metadata, and chat-template logic in one artifact. An adversary can modify a template and redistribute the artifact; when a lexical, semantic, or contextual trigger occurs, the template injects attacker-controlled instructions into the context sent to the model.

The attack was validated across eighteen models from seven families and four inference engines. In controlled evaluations, it manipulated model responses, redirected agent tool use, exfiltrated sensitive data, and inserted attacker-controlled code into generated software.

**Type**  Exercise

**Target**  Model registries distributing models in GGUF format

**Activity period**  2025-06

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.001%20-%20Models/README.md)

The adversary obtains a legitimate open-weight model artifact containing a bundled chat template. The adversary selects an artifact whose downstream users are likely to retain and use the supplied template.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.000 - Adversarial AI Attacks](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.000%20-%20Adversarial%20AI%20Attacks/README.md)

The adversary develops a template-based backdoor containing conditional trigger logic and an attacker-controlled instruction payload. The trigger is selected to activate during ordinary use of the intended application.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0018.003 - Modify Prompt Construction Logic](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.003%20-%20Modify%20Prompt%20Construction%20Logic/README.md)

The adversary modifies the chat template bundled with the model artifact. The modified template injects attacker-controlled instructions into the model context when its trigger is present, while leaving the model weights unchanged.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0074 - Masquerading](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0074%20-%20Masquerading/README.md)

The adversary makes the modified artifact appear equivalent to the legitimate model. The artifact preserves expected behavior when the trigger is absent, and the malicious logic is concealed among legitimate template formatting and control logic.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0115.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.001%20-%20Models/README.md)

The adversary publishes the modified model artifact through a model repository or another distribution channel used by downstream developers and organizations.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.003 - Model Repository](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md)

A victim downloads and integrates the poisoned artifact while trusting the model and its bundled components. This introduces the template backdoor into the victim's AI application or agent.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.000 - Unsafe AI Artifacts](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md)

The victim loads and uses the poisoned artifact in a compatible inference engine. During inference, the engine automatically interprets the bundled chat template, causing the attacker-modified prompt-construction logic to execute as part of normal model use.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.002 - Triggered](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.002%20-%20Triggered/README.md)

When a designated phrase or contextual condition appears, the template injects the attacker-controlled instruction into the serialized model context. The victim's ordinary activity activates the backdoor without requiring additional attacker interaction.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0031 - Erode AI Model Integrity](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md)

The injected instruction causes the model to produce plausible but incorrect or attacker-influenced responses. The model continues to behave normally when the trigger is absent, making the integrity compromise difficult to detect.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0067 - LLM Trusted Output Components Manipulation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0067%20-%20LLM%20Trusted%20Output%20Components%20Manipulation/README.md)

The injected instruction causes the model to include attacker-selected links, references, or other response components in a form that appears relevant or trustworthy to the user.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

When the poisoned model operates as part of an AI agent, the injected instruction redirects the agent's tool selection, tool arguments, or execution order toward the attacker's objective while allowing the legitimate task to continue.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

The compromised agent invokes a network-capable or write-capable tool to transmit sensitive information to an attacker-controlled destination. The agent may then continue and complete the user's legitimate task, concealing the unauthorized transmission.

**Next**  [S12](#step-s12)

### Step S12

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

The compromised system may expose users to privacy loss, credential theft, misleading information, or attacker-modified software. Malicious content inserted into generated artifacts may continue to affect downstream users after those artifacts are deployed or distributed.

**Next**  End of path

## Attributed to

- [AML.E0017 - Pillar Security](../../Entities/AML.E0017%20-%20Pillar%20Security.md) (Security Evaluation)
- [AML.E0033 - Fujitsu](../../Entities/AML.E0033%20-%20Fujitsu.md) (Security Evaluation)

## References

- [LLM Backdoors at the Inference Level: The Threat of Poisoned Templates](https://www.pillar.security/blog/llm-backdoors-at-the-inference-level-the-threat-of-poisoned-templates)
- [Inference-Time Backdoors via Chat Templates: From LLM Supply Chains to Agentic System Compromise](https://arxiv.org/abs/2602.04653)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0064)
