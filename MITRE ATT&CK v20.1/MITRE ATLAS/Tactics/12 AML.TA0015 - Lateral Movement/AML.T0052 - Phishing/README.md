# AML.T0052 - Phishing

[MITRE ATLAS](../../../README.md) / [AML.TA0015 - Lateral Movement](../README.md)

Adversaries may send phishing messages to gain access to victim systems. All forms of phishing are electronically delivered social engineering. Phishing can be targeted, known as spearphishing. In spearphishing, a specific individual, company, or industry will be targeted by the adversary. More generally, adversaries can conduct non-targeted phishing, such as in mass malware spam campaigns.

Generative AI, including LLMs that generate synthetic text, visual deepfakes of faces, and audio deepfakes of speech (See [Generate Deepfakes](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md)), is enabling adversaries to scale targeted phishing campaigns (See [Spearphishing via Social Engineering LLM](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/AML.T0052.000%20-%20Spearphishing%20via%20Social%20Engineering%20LLM/README.md)). LLMs can interact with users via text conversations and can be programmed with a system prompt to phish for sensitive information. Deepfakes can also be used in [Impersonation](../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0073%20-%20Impersonation/README.md) as an aid to phishing.

**Tactics**  [AML.TA0004 - Initial Access](../../04%20AML.TA0004%20-%20Initial%20Access/README.md), [AML.TA0015 - Lateral Movement](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1566](../../../../Enterprise/Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/README.md) · [MITRE ATT&CK T1566](https://attack.mitre.org/techniques/T1566/)

## Sub-techniques

- [AML.T0052.001 - Deepfake-Assisted Phishing](AML.T0052.001%20-%20Deepfake-Assisted%20Phishing/README.md)
- [AML.T0052.000 - Spearphishing via Social Engineering LLM](AML.T0052.000%20-%20Spearphishing%20via%20Social%20Engineering%20LLM/README.md)

## Case studies

- [AML.CS0032 - Attempted Evasion of ML Phishing Webpage Detection System](../../../Case%20Studies/Incidents/AML.CS0032%20-%20Attempted%20Evasion%20of%20ML%20Phishing%20Webpage%20Detection%20System.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0032%20-%20Attempted%20Evasion%20of%20ML%20Phishing%20Webpage%20Detection%20System.md#step-s02)
- [AML.CS0044 - LAMEHUG: Malware Leveraging Dynamic AI-Generated Commands](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md#step-s01)

## Mitigations

- [AML.M0018 - User Training](../../../Mitigations/AML.M0018%20-%20User%20Training.md) — Train users to identify phishing attempts by an adversary to reduce the risk of successful spearphishing, social engineering, and other techniques that involve user interaction.
- [AML.M0034 - Deepfake Detection](../../../Mitigations/AML.M0034%20-%20Deepfake%20Detection.md) — Deepfake detection can be used to identify and block phishing attempts that use generated content.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0052)
