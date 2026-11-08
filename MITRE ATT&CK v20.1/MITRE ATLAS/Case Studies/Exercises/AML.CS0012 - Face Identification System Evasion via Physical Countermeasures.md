# AML.CS0012 - Face Identification System Evasion via Physical Countermeasures

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

MITRE's AI Red Team demonstrated a physical-domain evasion attack on a commercial face identification service with the intention of inducing a targeted misclassification.
This operation had a combination of traditional MITRE ATT&CK techniques such as finding valid accounts and executing code via an API - all interleaved with adversarial ML specific attacks.

**Type**  Exercise

**Target**  Commercial Face Identification Service

**Activity period**  2020-01-01

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0000 - Search Open Technical Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)

The team first performed reconnaissance to gather information about the target ML model.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

The team gained access to the commercial face identification service and its API through a valid account.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0040 - AI Model Inference API Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md)

The team accessed the inference API of the target model.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0013 - Discover AI Model Ontology](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0013%20-%20Discover%20AI%20Model%20Ontology/README.md)

The team identified the list of identities targeted by the model by querying the target model's inference API.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002.000 - Datasets](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.000%20-%20Datasets/README.md)

The team acquired representative open source data.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0005 - Replicate AI Model Behavior](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md)

The team developed a proxy model using the open source data.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.000 - White-Box Optimization](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.000%20-%20White-Box%20Optimization/README.md)

Using the proxy model, the red team optimized adversarial visual patterns as a physical domain patch-based attack using expectation over transformation.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.003 - Physical Countermeasures](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.003%20-%20Physical%20Countermeasures/README.md)

The team printed the optimized patch.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0041 - Physical Environment Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0041%20-%20Physical%20Environment%20Access/README.md)

The team placed the countermeasure in the physical environment to cause issues in the face identification system.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0015%20-%20Evade%20AI%20Model/README.md)

The team successfully evaded the model using the physical countermeasure by causing targeted misclassifications.

**Next**  End of path

## Attributed to

- [AML.E0000 - MITRE AI Red Team](../../Entities/AML.E0000%20-%20MITRE%20AI%20Red%20Team.md) (Security Evaluation)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0012)
