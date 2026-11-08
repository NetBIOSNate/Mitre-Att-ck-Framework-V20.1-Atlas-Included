# AML.T0018 - Manipulate AI Model

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Adversaries may manipulate an AI model artifact or its bundled components to change AI system behavior, introduce malicious code, or establish persistent malicious functionality. This may include modifying model weights, model architecture, or prompt-construction logic.  

Manipulated artifacts may retain expected behavior under ordinary conditions while activating malicious behavior only for selected inputs, contexts, or deployment conditions.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md), [AML.TA0006 - Persistence](../../07%20AML.TA0006%20-%20Persistence/README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0018.002 - Embed Malware](AML.T0018.002%20-%20Embed%20Malware/README.md)
- [AML.T0018.001 - Modify AI Model Architecture](AML.T0018.001%20-%20Modify%20AI%20Model%20Architecture/README.md)
- [AML.T0018.003 - Modify Prompt Construction Logic](AML.T0018.003%20-%20Modify%20Prompt%20Construction%20Logic/README.md)
- [AML.T0018.000 - Poison AI Model](AML.T0018.000%20-%20Poison%20AI%20Model/README.md)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can prevent tampering with AI artifacts and prevent unauthorized modification.
- [AML.M0008 - Validate AI Model](../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models against trusted baselines and representative adversarial inputs for behavior consistent with manipulation. Investigate unexplained regressions or input-dependent behavior and restrict deployment until findings are resolved.
- [AML.M0013 - Code Signing](../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Code signing provides a guarantee that the model has not been manipulated after signing took place.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Attempt controlled modification or substitution of models, weights, adapters, and related configuration. Remediate weaknesses in authorization, artifact integrity, deployment approval, monitoring, and recovery.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0018)
