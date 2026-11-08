# AML.M0005 - Control Access to AI Models and Data at Rest

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Establish access controls on internal model registries and limit internal access to production models. Limit access to training data only to approved users.

**Mitigation categories**  Policy

**Lifecycle phases**  Business and Data Understanding, Data Preparation, AI Model Engineering, AI Model Evaluation

## Techniques mitigated

- [AML.T0007 - Discover AI Artifacts](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0007%20-%20Discover%20AI%20Artifacts/README.md) — Access controls can limit an adversary's ability to identify AI models, datasets, and other artifacts on a system.
- [AML.T0010.002 - Data Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.002%20-%20Data%20Repository/README.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.T0010.003 - Model Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.T0012 - Valid Accounts](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md) — Restrict model registries and training data to approved identities so compromised accounts expose only explicitly authorized AI assets.
- [AML.T0018 - Manipulate AI Model](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/README.md) — Access controls can prevent tampering with AI artifacts and prevent unauthorized modification.
- [AML.T0018.000 - Poison AI Model](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.T0018.001 - Modify AI Model Architecture](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.001%20-%20Modify%20AI%20Model%20Architecture/README.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.T0020 - Training Data Poisoning](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.T0021 - Establish Accounts](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md) — Verify identities before granting access to model registries so newly established accounts cannot automatically access protected AI artifacts.
- [AML.T0025 - Exfiltration via Cyber Means](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md) — Access controls can prevent exfiltration.
- [AML.T0035 - AI Artifact Collection](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md) — Access controls can prevent or limit the collection of AI artifacts on the victim system.
- [AML.T0042 - Verify Attack](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md) — Access controls on models at rest can prevent an adversary's ability to verify attack efficacy.
- [AML.T0043.000 - White-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.000%20-%20White-Box%20Optimization/README.md) — Access controls can reduce unnecessary access to AI models and prevent an adversary from achieving white-box access.
- [AML.T0044 - Full AI Model Access](../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0044%20-%20Full%20AI%20Model%20Access/README.md) — Access controls on models and data at rest can help prevent full model access.
- [AML.T0048.004 - AI Intellectual Property Theft](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md) — Access controls can prevent theft of intellectual property.
- [AML.T0069 - Discover LLM System Information](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/README.md) — Restrict access to stored system prompts, configuration files, and model metadata.
- [AML.T0069.000 - Special Character Sets](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/AML.T0069.000%20-%20Special%20Character%20Sets/README.md) — Restrict access to stored prompt templates and configurations containing internal delimiters.
- [AML.T0069.001 - System Instruction Keywords](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/AML.T0069.001%20-%20System%20Instruction%20Keywords/README.md) — Restrict access to stored system instructions and tool definitions containing privileged keywords.
- [AML.T0069.002 - System Prompt](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/AML.T0069.002%20-%20System%20Prompt/README.md) — Restrict access to stored system prompts and prompt templates.
- [AML.T0112.001 - AI Artifacts](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0112%20-%20Machine%20Compromise/AML.T0112.001%20-%20AI%20Artifacts/README.md) — Restrict write access to model registries and AI artifact stores.
- [AML.T0120 - AI Artifact Repository](../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0120%20-%20AI%20Artifact%20Repository/README.md) — Control access to AI assets at rest to prevent an adversary from repurposing these channels for command and control.
- [AML.T0126 - Automated Collection](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0126%20-%20Automated%20Collection/README.md) — Restrict access to model repositories, training data, and other AI resources to prevent or limit collection.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0005)
