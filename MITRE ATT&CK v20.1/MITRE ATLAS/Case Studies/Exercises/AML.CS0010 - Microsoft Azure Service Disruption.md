# AML.CS0010 - Microsoft Azure Service Disruption

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

The Microsoft AI Red Team performed a red team exercise on an internal Azure service with the intention of disrupting its service. This operation had a combination of traditional ATT&CK enterprise techniques such as finding valid account, and exfiltrating data -- all interleaved with adversarial ML specific steps such as offline and online evasion examples.

**Type**  Exercise

**Target**  Internal Microsoft Azure Service

**Activity period**  2020

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0000 - Search Open Technical Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)

The team first performed reconnaissance to gather information about the target ML model.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

The team used a valid account to gain access to the network.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0035 - AI Artifact Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md)

The team found the model file of the target ML model and the necessary training data.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

The team exfiltrated the model and data via traditional means.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.000 - White-Box Optimization](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.000%20-%20White-Box%20Optimization/README.md)

Using the target model and data, the red team crafted evasive adversarial data in an offline manner.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0040 - AI Model Inference API Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md)

The team used an exposed API to access the target model.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0042 - Verify Attack](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md)

The team submitted the adversarial examples to the API to verify their efficacy on the production system.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0015%20-%20Evade%20AI%20Model/README.md)

The team performed an online evasion attack by replaying the adversarial examples and accomplished their goals.

**Next**  End of path

## Attributed to

- [AML.E0001 - Microsoft AI Red Team](../../Entities/AML.E0001%20-%20Microsoft%20AI%20Red%20Team.md) (Security Evaluation)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0010)
