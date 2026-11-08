# AML.T0018.000 - Poison AI Model

[MITRE ATLAS](../../../../README.md) / [AML.TA0006 - Persistence](../../README.md) / [AML.T0018 - Manipulate AI Model](../README.md)

Adversaries may manipulate an AI model's weights to change it's behavior or performance, resulting in a poisoned model.
Adversaries may poison a model by directly manipulating its weights, training the model on poisoned data, further fine-tuning the model, or otherwise interfering with its training process. 

The change in behavior of poisoned models may be limited to targeted categories in predictive AI models, or targeted topics, concepts, or facts in generative AI models, or aim for a general performance degradation.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md), [AML.TA0006 - Persistence](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0019 - PoisonGPT](../../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md) · [S01](../../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md#step-s01)
- [AML.CS0027 - Organization Confusion on Hugging Face](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S14](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s14)
- [AML.CS0028 - AI Model Tampering via Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md#step-s05)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.M0007 - Sanitize Training Data](../../../../Mitigations/AML.M0007%20-%20Sanitize%20Training%20Data.md) — Screen training data for poisoning that could introduce malicious model behavior. Quarantine and remediate affected data before training.
- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate trained and acquired models using clean evaluation data and targeted tests for backdoors, prediction bias, and other poisoning effects. Include measures beyond aggregate accuracy, which may remain normal in poisoned models.
- [AML.M0013 - Code Signing](../../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Code signing provides a guarantee that the model has not been manipulated after signing took place.
- [AML.M0014 - Verify AI Artifacts](../../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify model weights and checkpoints against protected approval records before loading or deployment. Reject unauthorized substitutions or changes made after approval.
- [AML.M0023 - Maintain an AI Bill of Materials](../../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Record relationships between base models, checkpoints, fine-tuned derivatives, and deployed applications. Use these records to trace poisoned model versions to potentially affected derivatives and deployments and guide evaluation, replacement, or retraining.
- [AML.M0025 - Maintain AI Dataset Provenance](../../../../Mitigations/AML.M0025%20-%20Maintain%20AI%20Dataset%20Provenance.md) — Dataset provenance can protect against poisoning of models.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Test whether controlled changes to model weights, fine-tuning, or associated artifacts can introduce targeted or persistent behavior. Improve model provenance, validation, integrity monitoring, and rollback.

## Software implementations

- [AML.S0005 - ROME](../../../../Software/Tools/AML.S0005%20-%20ROME.md) — [ROME](../../../../Software/Tools/AML.S0005%20-%20ROME.md) directly updates a model's multilayer perceptron weights to replace a selected factual association. Mithril Security used it to encode a false Moon-landing association in GPT-J-6B while producing little change in the model's measured ToxiGen performance. [github](https://github.com/kmeng01/rome) [mithril](https://blog.mithrilsecurity.io/poisongpt-how-we-hid-a-lobotomized-llm-on-hugging-face-to-spread-fake-news/)
- [AML.S0006 - EasyEdit](../../../../Software/Tools/AML.S0006%20-%20EasyEdit.md) — [EasyEdit](../../../../Software/Tools/AML.S0006%20-%20EasyEdit.md) provides model editing methods that update selected model parameters to change factual associations or other targeted behavior. [github](https://github.com/zjunlp/EasyEdit)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0018.000)
