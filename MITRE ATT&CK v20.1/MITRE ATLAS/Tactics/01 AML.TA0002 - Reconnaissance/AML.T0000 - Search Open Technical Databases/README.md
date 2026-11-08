# AML.T0000 - Search Open Technical Databases

[MITRE ATLAS](../../../README.md) / [AML.TA0002 - Reconnaissance](../README.md)

Adversaries may search for publicly available research and technical documentation to learn how and where AI is used within a victim organization. The adversary can use this information to identify targets for attack, or to tailor an existing attack to make it more effective. Organizations often use open source model architectures trained on additional proprietary data in production. Knowledge of this underlying architecture allows the adversary to craft more realistic proxy models ([Replicate AI Model Behavior](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md)). An adversary can search these resources for publications for authors employed at the victim organization.

Research and technical materials may exist as academic papers published in [Journals and Conference Proceedings](AML.T0000.000%20-%20Journals%20and%20Conference%20Proceedings/README.md) or stored in [Pre-Print Repositories](AML.T0000.001%20-%20Pre-Print%20Repositories/README.md), as well as [Technical Blogs](AML.T0000.002%20-%20Technical%20Blogs/README.md). Publicly accessible AI services may be identified via [Scan Databases](AML.T0000.003%20-%20Scan%20Databases/README.md).

**Tactics**  [AML.TA0002 - Reconnaissance](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1596](../../../../Enterprise/Tactics/01%20TA0043%20-%20Reconnaissance/T1596%20-%20Search%20Open%20Technical%20Databases/README.md) · [MITRE ATT&CK T1596](https://attack.mitre.org/techniques/T1596/)

## Sub-techniques

- [AML.T0000.000 - Journals and Conference Proceedings](AML.T0000.000%20-%20Journals%20and%20Conference%20Proceedings/README.md)
- [AML.T0000.001 - Pre-Print Repositories](AML.T0000.001%20-%20Pre-Print%20Repositories/README.md)
- [AML.T0000.003 - Scan Databases](AML.T0000.003%20-%20Scan%20Databases/README.md)
- [AML.T0000.002 - Technical Blogs](AML.T0000.002%20-%20Technical%20Blogs/README.md)

## Case studies

- [AML.CS0001 - Botnet Domain Generation Algorithm (DGA) Detection Evasion](../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md#step-s00)
- [AML.CS0003 - Bypassing Cylance's AI Malware Detection](../../../Case%20Studies/Exercises/AML.CS0003%20-%20Bypassing%20Cylance's%20AI%20Malware%20Detection.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0003%20-%20Bypassing%20Cylance's%20AI%20Malware%20Detection.md#step-s00)
- [AML.CS0005 - Attack on Machine Translation Services](../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md#step-s00)
- [AML.CS0007 - GPT-2 Model Replication](../../../Case%20Studies/Exercises/AML.CS0007%20-%20GPT-2%20Model%20Replication.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0007%20-%20GPT-2%20Model%20Replication.md#step-s00)
- [AML.CS0010 - Microsoft Azure Service Disruption](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md#step-s00)
- [AML.CS0011 - Microsoft Edge AI Evasion](../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md#step-s00)
- [AML.CS0012 - Face Identification System Evasion via Physical Countermeasures](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md#step-s00)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S15](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s15)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Limit the connection between publicly disclosed approaches and the data, models, and algorithms used in production.
- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Decoy assets are catalogued by the same internet scan databases (e.g., Shodan, Censys) that adversaries query to locate exposed AI infrastructure. Adversarial engagement that originates from those platforms can grant defenders visibility into those discovery channels.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0000)
