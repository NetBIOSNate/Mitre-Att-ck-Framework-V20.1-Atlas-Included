# AML.T0018.001 - Modify AI Model Architecture

[MITRE ATLAS](../../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../../README.md) / [AML.T0018 - Manipulate AI Model](../README.md)

Adversaries may directly modify an AI model's architecture to re-define it's behavior. This can include adding or removing layers as well as adding pre or post-processing operations.

The effects could include removing the ability to predict certain classes, adding erroneous operations to increase computation costs, or degrading performance. Additionally, a separate adversary-defined network could be injected into the computation graph, which can change the behavior based on the inputs, effectively creating a backdoor.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../README.md), [AML.TA0006 - Persistence](../../../07%20AML.TA0006%20-%20Persistence/README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps](../../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md#step-s04)
- [AML.CS0028 - AI Model Tampering via Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md#step-s06)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models against trusted baselines for changes in class coverage, predictions, input-dependent behavior, or resource consumption caused by architecture or preprocessing modifications. Investigate unexplained deviations before deployment.
- [AML.M0013 - Code Signing](../../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Code signing provides a guarantee that the model has not been manipulated after signing took place.
- [AML.M0014 - Verify AI Artifacts](../../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify model architecture definitions against approved manifests before loading or deployment. Reject unauthorized changes even when model weights remain unchanged.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Attempt controlled unauthorized changes to model architecture or executable model components. Verify review, integrity checking, signing, deployment approval, and restoration controls.

## Software implementations

- [AML.S0003 - DeepPayload](../../../../Software/Tools/AML.S0003%20-%20DeepPayload.md) — [DeepPayload](../../../../Software/Tools/AML.S0003%20-%20DeepPayload.md) modifies a compiled model's computation graph by adding a trigger detector and a conditional branch between its input and output. The branch selects an attacker-defined output when the trigger is present and the original model's output otherwise. It recompiles the modified graph into a replacement model without retraining the original model. [github](https://github.com/yuanchun-li/DeepPayload)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0018.001)
