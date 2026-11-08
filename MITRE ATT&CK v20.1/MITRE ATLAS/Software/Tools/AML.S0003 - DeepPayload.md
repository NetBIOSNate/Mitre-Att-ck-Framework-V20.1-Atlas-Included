# AML.S0003 - DeepPayload

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[DeepPayload](AML.S0003%20-%20DeepPayload.md) is research software for injecting backdoors into compiled deep learning models without retraining the original model. It combines a separately trained trigger detector with conditional operations inserted into the model's computation graph. When a trigger is detected, the modified model substitutes an adversary-specified output; otherwise, it retains the original model's output. [arxiv](https://arxiv.org/abs/2101.06896) [github](https://github.com/yuanchun-li/DeepPayload)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps](../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md) — The researchers used [DeepPayload](AML.S0003%20-%20DeepPayload.md) to inject trigger detectors and conditional output-selection operations into models extracted from Android applications. They replaced the original models with the backdoored versions and repackaged the applications. Of 116 applications tested, 54 continued operating without crashing after model replacement. [ref-1](https://arxiv.org/abs/2101.06896)

## Techniques implemented

- [AML.T0018.001 - Modify AI Model Architecture](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.001%20-%20Modify%20AI%20Model%20Architecture/README.md) — [DeepPayload](AML.S0003%20-%20DeepPayload.md) modifies a compiled model's computation graph by adding a trigger detector and a conditional branch between its input and output. The branch selects an attacker-defined output when the trigger is present and the original model's output otherwise. It recompiles the modified graph into a replacement model without retraining the original model. [github](https://github.com/yuanchun-li/DeepPayload)

## References

- [DeepPayload GitHub](https://github.com/yuanchun-li/DeepPayload)
- [DeepPayload: Black-box Backdoor Attack on Deep Learning Models through Neural Payload Injection](https://arxiv.org/abs/2101.06896)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0003)
