# AML.M0034 - Deepfake Detection

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Apply deepfake detection algorithms against any untrusted or user-provided data, especially in impactful applications such as biometric verification, to block generated content.

Detectors may use a combination of approaches, including:
- AI models trained to differentiate between real and deepfake content.
- Identifying common inconsistencies in deepfake content, such as unnatural facial movements, audio mismatches, or pixel-level artifacts.
- Biometrics analysis, such blinking, eye movements, and microexpressions.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  AI Model Engineering, AI Model Evaluation, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0015 - Evade AI Model](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md) — Deepfake detection can be used to identify and block generated content.
- [AML.T0052 - Phishing](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md) — Deepfake detection can be used to identify and block phishing attempts that use generated content.
- [AML.T0052.000 - Spearphishing via Social Engineering LLM](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/AML.T0052.000%20-%20Spearphishing%20via%20Social%20Engineering%20LLM/README.md) — Deepfake detection can be used to identify and block phishing attempts that use generated content.
- [AML.T0052.001 - Deepfake-Assisted Phishing](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/AML.T0052.001%20-%20Deepfake-Assisted%20Phishing/README.md) — Deploy technical controls to detect and block synthetic audio and video. This includes AI-based analysis tools that examine media for artifacts indicative deepfakes.
- [AML.T0088 - Generate Deepfakes](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md) — Deepfake detection can be used to identify and block generated content.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0034)
