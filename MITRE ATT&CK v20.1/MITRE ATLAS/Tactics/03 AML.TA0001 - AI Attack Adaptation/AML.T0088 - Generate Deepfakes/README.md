# AML.T0088 - Generate Deepfakes

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Adversaries may use generative artificial intelligence (GenAI) to create synthetic media (i.e. imagery, video, audio, and text) that appear authentic. These "[deepfakes]( https://en.wikipedia.org/wiki/Deepfake)" may mimic a real person or depict fictional personas. Adversaries may use deepfakes for impersonation to conduct [Phishing](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md) or to evade AI applications such as biometric identity verification systems (see [Evade AI Model](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md)).

Manipulation of media has been possible for a long time, however GenAI reduces the skill and level of effort required, allowing adversaries to rapidly scale operations to target more users or systems. It also makes real-time manipulations feasible.

Adversaries may utilize open-source models and software that were designed for legitimate use cases to generate deepfakes for malicious use. However, there are some projects specifically tailored towards malicious use cases such as [ProKYC](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/).

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0033 - Live Deepfake Image Injection to Evade Mobile KYC Verification](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md#step-s04)
- [AML.CS0034 - ProKYC: Deepfake Tool for Account Fraud Attacks](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md#step-s02), [S03](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md#step-s03)
- [AML.CS0057 - Storm-2139 Azure OpenAI Guardrail Bypass](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md#step-s06)

## Mitigations

- [AML.M0009 - Predictive AI Multi-Sensor Fusion](../../../Mitigations/AML.M0009%20-%20Predictive%20AI%20Multi-Sensor%20Fusion.md) — Using a variety of sensors, such as IR depth cameras, can aid in detecting deepfakes.
- [AML.M0034 - Deepfake Detection](../../../Mitigations/AML.M0034%20-%20Deepfake%20Detection.md) — Deepfake detection can be used to identify and block generated content.

## Software implementations

- [AML.S0012 - ProKYC](../../../Software/Tools/AML.S0012%20-%20ProKYC.md) — [ProKYC](../../../Software/Tools/AML.S0012%20-%20ProKYC.md) generates synthetic facial videos from supplied images, animating head movements to resemble a person completing a facial-verification challenge. The generated face matches the image incorporated into the forged identity document. [cato](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)
- [AML.S0013 - Swapface](../../../Software/Tools/AML.S0013%20-%20Swapface.md) — [Swapface](../../../Software/Tools/AML.S0013%20-%20Swapface.md) replaces a person's face in a live video feed with a selected facial image, generating real-time face-swapped video that can be delivered to other applications through a virtual camera. [source-1](https://swapface.org/)
- [AML.S0020 - de3u](../../../Software/Tools/AML.S0020%20-%20de3u.md) — According to Microsoft, users employed [de3u](../../../Software/Tools/AML.S0020%20-%20de3u.md) to submit image-generation requests to DALL-E through Azure OpenAI Service and generate non-consensual intimate images of celebrities. [microsoft-complaint](https://www.akingump.com/a/web/tA6v8pfayLrekvqFsLVwXT/microsoft-vs-storm-2139.pdf)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0088)
