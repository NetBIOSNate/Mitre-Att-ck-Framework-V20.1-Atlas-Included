# AML.T0127 - Data Staged

[MITRE ATLAS](../../../README.md) / [AML.TA0009 - Collection](../README.md)

Adversaries may stage collected data in a central location before exfiltration. Staging consolidates, organizes, or prepares information obtained from one or more sources so it can be reviewed, processed, transferred, or retrieved more efficiently.

Data may be staged on a compromised local system, another system in the victim environment, a cloud instance, shared storage, an application repository, or other remote infrastructure. It may remain in separate files or be combined into archives, databases, structured documents, manifests, or other collections. Adversaries may compress, encrypt, encode, split, rename, or otherwise transform staged data.

**Tactics**  [AML.TA0009 - Collection](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1074](../../../../Enterprise/Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/README.md) · [MITRE ATT&CK T1074](https://attack.mitre.org/techniques/T1074/)

## Case studies

- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S20](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s20)

## Mitigations

- [AML.M0043 - AI Agent External Resource Lifecycle Management](../../../Mitigations/AML.M0043%20-%20AI%20Agent%20External%20Resource%20Lifecycle%20Management.md) — Remove staged data and revoke access to managed staging locations to limit subsequent retrieval and exfiltration.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0127)
