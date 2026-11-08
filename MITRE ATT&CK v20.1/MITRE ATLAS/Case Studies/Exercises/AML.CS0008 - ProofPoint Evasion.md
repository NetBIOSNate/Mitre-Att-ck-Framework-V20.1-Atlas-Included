# AML.CS0008 - ProofPoint Evasion

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Proof Pudding (CVE-2019-20634) is a code repository that describes how ML researchers evaded ProofPoint's email protection system by first building a copy-cat email protection ML model, and using the insights to bypass the live system. More specifically, the insights allowed researchers to craft malicious emails that received preferable scores, going undetected by the system. Each word in an email is scored numerically based on multiple variables and if the overall score of the email is too low, ProofPoint will output an error, labeling it as SPAM.

**Type**  Exercise

**Target**  ProofPoint Email Protection System

**Activity period**  2019-09-09

## Procedure steps

### Step S00

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0063 - Discover AI Model Outputs](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0063%20-%20Discover%20AI%20Model%20Outputs/README.md)

The researchers discovered that ProofPoint's Email Protection left model output scores in email headers.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0135 - Outputs from AI Models](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md)

The researchers sent many emails through the system to collect model outputs from the headers.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0005.001 - Replicate Behavior from Model Outputs](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md)

The researchers used the emails and collected scores as a dataset, which they used to train a functional copy of the ProofPoint model. 

Basic correlation was used to decide which score variable speaks generally about the security of an email. The "mlxlogscore" was selected in this case due to its relationship with spam, phish, and core mlx and was used as the label. Each "mlxlogscore" was generally between 1 and 999 (higher score = safer sample). Training was performed using an Artificial Neural Network (ANN) and Bag of Words tokenizing.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.002 - Black-Box Transfer](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.002%20-%20Black-Box%20Transfer/README.md)

Next, the ML researchers algorithmically found samples from this "offline" proxy model that helped give desired insight into its behavior and influential variables.

Examples of good scoring samples include "calculation", "asset", and "tyson".
Examples of bad scoring samples include "software", "99", and "unsub".

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0015%20-%20Evade%20AI%20Model/README.md)

Finally, these insights from the "offline" proxy model allowed the researchers to create malicious emails that received preferable scores from the real ProofPoint email protection system, hence bypassing it.

**Next**  End of path

## Attributed to

- [AML.E0002 - Silent Break Security](../../Entities/AML.E0002%20-%20Silent%20Break%20Security.md) (Security Evaluation)

## References

- [National Vulnerability Database entry for CVE-2019-20634](https://nvd.nist.gov/vuln/detail/CVE-2019-20634)
- [2019 DerbyCon presentation "42: The answer to life, the universe, and everything offensive security"](https://github.com/moohax/Talks/blob/master/slides/DerbyCon19.pdf)
- [Proof Pudding (CVE-2019-20634) Implementation on GitHub](https://github.com/moohax/Proof-Pudding)
- [2019 DerbyCon video presentation "42: The answer to life, the universe, and everything offensive security"](https://www.youtube.com/watch?v=CsvkYoxtexQ&ab-channel=AdrianCrenshaw)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0008)
