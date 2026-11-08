# AML.CS0011 - Microsoft Edge AI Evasion

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

The Azure Red Team performed a red team exercise on a new Microsoft product designed for running AI workloads at the edge. This exercise was meant to use an automated system to continuously manipulate a target image to cause the ML model to produce misclassifications.

**Type**  Exercise

**Target**  New Microsoft AI Product

**Activity period**  2020-02

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0000 - Search Open Technical Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)

The team first performed reconnaissance to gather information about the target ML model.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002 - Acquire Public AI Artifacts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/README.md)

The team identified and obtained the publicly available base model to use against the target ML model.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0040 - AI Model Inference API Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md)

Using the publicly available version of the ML model, the team started sending queries and analyzing the responses (inferences) from the ML model.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.001 - Black-Box Optimization](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md)

The red team created an automated system that continuously manipulated an original target image, that tricked the ML model into producing incorrect inferences, but the perturbations in the image were unnoticeable to the human eye.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0015%20-%20Evade%20AI%20Model/README.md)

Feeding this perturbed image, the red team was able to evade the ML model by causing misclassifications.

**Next**  End of path

## Attributed to

- [AML.E0001 - Microsoft AI Red Team](../../Entities/AML.E0001%20-%20Microsoft%20AI%20Red%20Team.md) (Security Evaluation)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0011)
