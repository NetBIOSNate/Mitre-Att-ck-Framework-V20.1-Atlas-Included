# AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Deep learning models are increasingly used in mobile applications as critical components.
Researchers from Microsoft Research demonstrated that many deep learning models deployed in mobile apps are vulnerable to backdoor attacks via "neural payload injection."
They conducted an empirical study on real-world mobile deep learning apps collected from Google Play. They identified 54 apps that were vulnerable to attack, including popular security and safety critical applications used for cash recognition, parental control, face authentication, and financial services.

**Type**  Exercise

**Actor**  Yuanchun Li, Jiayi Hua, Haoyu Wang, Chunyang Chen, Yunxin Liu

**Target**  ML-based Android Apps

**Activity period**  2021-01-18

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0004 - Search Application Repositories](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0004%20-%20Search%20Application%20Repositories/README.md)

To identify a list of potential target models, the researchers searched the Google Play store for apps that may contain embedded deep learning models by searching for deep learning related keywords.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.001%20-%20Models/README.md)

The researchers acquired the apps' APKs from the Google Play store.
They filtered the list of potential target applications by searching the code metadata for keywords related to TensorFlow or TFLite and their model binary formats (.tf and .tflite).
The models were extracted from the APKs using Apktool.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0044 - Full AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0044%20-%20Full%20AI%20Model%20Access/README.md)

This provided the researchers with full access to the ML model, albeit in compiled, binary form.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.000 - Adversarial AI Attacks](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.000%20-%20Adversarial%20AI%20Attacks/README.md)

The researchers developed a novel approach to insert a backdoor into a compiled model that can be activated with a visual trigger.  They inject a "neural payload" into the model that consists of a trigger detection network and conditional logic.
The trigger detector is trained to detect a visual trigger that will be placed in the real world.
The conditional logic allows the researchers to bypass the victim model when the trigger is detected and provide model outputs of their choosing.
The only requirements for training a trigger detector are a general
dataset from the same modality as the target model (e.g. ImageNet for image classification) and several photos of the desired trigger.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0018.001 - Modify AI Model Architecture](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.001%20-%20Modify%20AI%20Model%20Architecture/README.md)

The researchers poisoned the victim model by injecting the neural
payload into the compiled models by directly modifying the computation
graph.
The researchers then repackage the poisoned model back into the APK

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0042 - Verify Attack](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md)

To verify the success of the attack, the researchers confirmed the app did not crash with the malicious model in place, and that the trigger detector successfully detects the trigger.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.003 - Model Repository](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md)

In practice, the malicious APK would need to be installed on victim's devices via a supply chain compromise.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.004 - Insert Backdoor Trigger](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.004%20-%20Insert%20Backdoor%20Trigger/README.md)

The trigger is placed in the physical environment, where it is captured by the victim's device camera and processed by the backdoored ML model.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0041 - Physical Environment Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0041%20-%20Physical%20Environment%20Access/README.md)

At inference time, only physical environment access is required to trigger the attack.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0015%20-%20Evade%20AI%20Model/README.md)

Presenting the visual trigger causes the victim model to be bypassed.
The researchers demonstrated this can be used to evade ML models in
several safety-critical apps in the Google Play store.

**Next**  End of path

## Uses

- [AML.S0003 - DeepPayload](../../Software/Tools/AML.S0003%20-%20DeepPayload.md) — The researchers used [DeepPayload](../../Software/Tools/AML.S0003%20-%20DeepPayload.md) to inject trigger detectors and conditional output-selection operations into models extracted from Android applications. They replaced the original models with the backdoored versions and repackaged the applications. Of 116 applications tested, 54 continued operating without crashing after model replacement. [ref-1](https://arxiv.org/abs/2101.06896)

## References

- [DeepPayload: Black-box Backdoor Attack on Deep Learning Models through Neural Payload Injection](https://arxiv.org/abs/2101.06896)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0013)
