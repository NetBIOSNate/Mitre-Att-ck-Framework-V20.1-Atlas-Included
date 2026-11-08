# AML.T0015 - Evade AI Model

[MITRE ATLAS](../../../README.md) / [AML.TA0004 - Initial Access](../README.md)

Adversaries can [Craft Adversarial Data](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) that prevents an AI model from correctly identifying the contents of the data or [Generate Deepfakes](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md) that fools an AI model expecting authentic data.

This technique can be used to evade a downstream task where AI is utilized. The adversary may evade AI-based virus/malware detection or network scanning towards the goal of a traditional cyber attack. AI model evasion through deepfake generation may also provide initial access to systems that use AI-based biometric authentication.

**Tactics**  [AML.TA0004 - Initial Access](../README.md), [AML.TA0007 - Defense Evasion](../../09%20AML.TA0007%20-%20Defense%20Evasion/README.md), [AML.TA0011 - Impact](../../16%20AML.TA0011%20-%20Impact/README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0000 - Evasion of Deep Learning Detector for Malware C&C Traffic](../../../Case%20Studies/Exercises/AML.CS0000%20-%20Evasion%20of%20Deep%20Learning%20Detector%20for%20Malware%20C%26C%20Traffic.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0000%20-%20Evasion%20of%20Deep%20Learning%20Detector%20for%20Malware%20C%26C%20Traffic.md#step-s05)
- [AML.CS0001 - Botnet Domain Generation Algorithm (DGA) Detection Evasion](../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md#step-s05)
- [AML.CS0003 - Bypassing Cylance's AI Malware Detection](../../../Case%20Studies/Exercises/AML.CS0003%20-%20Bypassing%20Cylance's%20AI%20Malware%20Detection.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0003%20-%20Bypassing%20Cylance's%20AI%20Malware%20Detection.md#step-s05)
- [AML.CS0004 - Camera Hijack Attack on Facial Recognition System](../../../Case%20Studies/Incidents/AML.CS0004%20-%20Camera%20Hijack%20Attack%20on%20Facial%20Recognition%20System.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0004%20-%20Camera%20Hijack%20Attack%20on%20Facial%20Recognition%20System.md#step-s06)
- [AML.CS0005 - Attack on Machine Translation Services](../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md#step-s07)
- [AML.CS0008 - ProofPoint Evasion](../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md#step-s04)
- [AML.CS0010 - Microsoft Azure Service Disruption](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md#step-s07)
- [AML.CS0011 - Microsoft Edge AI Evasion](../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md#step-s04)
- [AML.CS0012 - Face Identification System Evasion via Physical Countermeasures](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md#step-s09)
- [AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps](../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md#step-s09)
- [AML.CS0014 - Confusing Antimalware Neural Networks](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md#step-s08)
- [AML.CS0017 - Bypassing ID.me Identity Verification](../../../Case%20Studies/Incidents/AML.CS0017%20-%20Bypassing%20ID.me%20Identity%20Verification.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0017%20-%20Bypassing%20ID.me%20Identity%20Verification.md#step-s01)
- [AML.CS0028 - AI Model Tampering via Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md#step-s08)
- [AML.CS0032 - Attempted Evasion of ML Phishing Webpage Detection System](../../../Case%20Studies/Incidents/AML.CS0032%20-%20Attempted%20Evasion%20of%20ML%20Phishing%20Webpage%20Detection%20System.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0032%20-%20Attempted%20Evasion%20of%20ML%20Phishing%20Webpage%20Detection%20System.md#step-s01)
- [AML.CS0033 - Live Deepfake Image Injection to Evade Mobile KYC Verification](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md#step-s07)
- [AML.CS0034 - ProKYC: Deepfake Tool for Account Fraud Attacks](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md#step-s06)
- [AML.CS0043 - Malware Prototype with Embedded Prompt Injection](../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md#step-s03)
- [AML.CS0058 - Google Photos AI Model Extraction](../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md#step-s05)

## Mitigations

- [AML.M0003 - Predictive AI Model Hardening](../../../Mitigations/AML.M0003%20-%20Predictive%20AI%20Model%20Hardening.md) — Hardened models are more difficult to evade.
- [AML.M0006 - Predictive AI Ensembles](../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Using multiple different models increases robustness to attack.
- [AML.M0008 - Validate AI Model](../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models against representative adversarial inputs for misclassification or missed detection under realistic operating conditions. Use failures against robustness acceptance criteria to guide model selection, remediation, or deployment restrictions.
- [AML.M0009 - Predictive AI Multi-Sensor Fusion](../../../Mitigations/AML.M0009%20-%20Predictive%20AI%20Multi-Sensor%20Fusion.md) — Using a variety of sensors can make it more difficult for an attacker to compromise and produce malicious results.
- [AML.M0010 - Predictive AI Input Restoration](../../../Mitigations/AML.M0010%20-%20Predictive%20AI%20Input%20Restoration.md) — Preprocessing model inputs can prevent malicious data from going through the machine learning pipeline.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Prevent an attacker from introducing adversarial data into the system.
- [AML.M0034 - Deepfake Detection](../../../Mitigations/AML.M0034%20-%20Deepfake%20Detection.md) — Deepfake detection can be used to identify and block generated content.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Execute representative digital, multimodal, and physical-domain evasion attacks. Use successful attacks to improve model robustness, preprocessing, adversarial-input detection, human oversight, and monitoring.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0015)
