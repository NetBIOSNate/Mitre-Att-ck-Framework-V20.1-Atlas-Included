# AML.M0025 - Maintain AI Dataset Provenance

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Maintain a detailed history of datasets used for AI applications. The history should include information about the dataset's source as well as a complete record of any modifications.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Business and Data Understanding, Data Preparation

## Techniques mitigated

- [AML.T0010.002 - Data Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.002%20-%20Data%20Repository/README.md) — Dataset provenance can protect against supply chain compromise of data.
- [AML.T0018.000 - Poison AI Model](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) — Dataset provenance can protect against poisoning of models.
- [AML.T0020 - Training Data Poisoning](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md) — Dataset provenance can protect against poisoning of training data
- [AML.T0059 - Erode Dataset Integrity](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0059%20-%20Erode%20Dataset%20Integrity/README.md) — Maintaining dataset provenance can help identify adverse changes to the data.
- [AML.T0074 - Masquerading](../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0074%20-%20Masquerading/README.md) — Record dataset sources and modification history so datasets falsely presented as trusted can be identified.
- [AML.T0145 - Poison AI Agent Learning Environment](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0145%20-%20Poison%20AI%20Agent%20Learning%20Environment/README.md) — Record the sources of environmental content and resulting interaction data used in learning or adaptation to trace suspicious learning experiences to their sources.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0025)
