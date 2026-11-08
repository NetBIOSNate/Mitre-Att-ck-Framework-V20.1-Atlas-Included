# AML.M0018 - User Training

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Educate AI model developers to on AI supply chain risks and potentially malicious AI artifacts.
Educate users on how to identify deepfakes and phishing attempts.

**ATT&CK mapping**  [Local ATT&CK M1017](../../Enterprise/Defenses/Mitigations/M1017%20-%20User%20Training.md) · [MITRE ATT&CK M1017](https://attack.mitre.org/mitigations/M1017/)

**Mitigation categories**  Policy

**Lifecycle phases**  Business and Data Understanding, Data Preparation, AI Model Engineering, AI Model Evaluation, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0011 - User Execution](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/README.md) — Training users to be able to identify attempts at manipulation will make them less susceptible to performing techniques that cause the execution of malicious code.
- [AML.T0011.000 - Unsafe AI Artifacts](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md) — Train users to identify attempts of manipulation to prevent them from running unsafe code which when executed could develop unsafe artifacts. These artifacts may have a detrimental effect on the system.
- [AML.T0011.001 - Malicious Package](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.001%20-%20Malicious%20Package/README.md) — Train users to identify attempts of manipulation to prevent them from running unsafe code from external packages.
- [AML.T0052 - Phishing](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md) — Train users to identify phishing attempts by an adversary to reduce the risk of successful spearphishing, social engineering, and other techniques that involve user interaction.
- [AML.T0052.000 - Spearphishing via Social Engineering LLM](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/AML.T0052.000%20-%20Spearphishing%20via%20Social%20Engineering%20LLM/README.md) — Train users to identify phishing attempts and understand that AI can be used to generate targeted and convincing messages.
- [AML.T0052.001 - Deepfake-Assisted Phishing](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/AML.T0052.001%20-%20Deepfake-Assisted%20Phishing/README.md) — Train users on deepfake threats, including how to recognize synthetic voice, video, and text. Recommend verification through independent channels (e.g. known call-back number) before processing sensitive requests or providing sensitive information via voice or video calls.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0018)
