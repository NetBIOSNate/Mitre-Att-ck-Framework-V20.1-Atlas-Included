# AML.CS0025 - Web-Scale Data Poisoning: Split-View Attack

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Many recent large-scale datasets are distributed as a list of URLs pointing to individual datapoints. The researchers show that many of these datasets are vulnerable to a "split-view" poisoning attack. The attack exploits the fact that the data viewed when it was initially collected may differ from the data viewed by a user during training. The researchers identify expired and buyable domains that once hosted dataset content, making it possible to replace portions of the dataset with poisoned data. They demonstrate that for 10 popular web-scale datasets, enough of the domains are purchasable to successfully carry out a poisoning attack.

**Type**  Exercise

**Actor**  Researchers from Google Deepmind, ETH Zurich, NVIDIA, Robust Intelligence, and Google

**Target**  10 web-scale datasets

**Activity period**  2022-08 to 2023-08

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002.000 - Datasets](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.000%20-%20Datasets/README.md)

The researchers download a web-scale dataset, which consists of URLs pointing to individual datapoints.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.002 - Domains](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.002%20-%20Domains/README.md)

They identify expired domains in the dataset and purchase them.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0020 - Training Data Poisoning](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md)

An adversary could create poisoned training data to replace expired portions of the dataset.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0115.000 - Datasets](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.000%20-%20Datasets/README.md)

An adversary could then upload the poisoned data to the domains they control.  In this particular exercise, the researchers track requests to the URLs they control to track downloads to demonstrate there are active users of the dataset.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0059 - Erode Dataset Integrity](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0059%20-%20Erode%20Dataset%20Integrity/README.md)

The integrity of the dataset has been eroded because future downloads would contain poisoned datapoints.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0031 - Erode AI Model Integrity](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md)

Models that use the dataset for training data are poisoned, eroding model integrity. The researchers show as little as 0.01% of the data needs to be poisoned for a successful attack.

**Next**  End of path

## References

- [Poisoning Web-Scale Training Datasets is Practical](https://arxiv.org/pdf/2302.10149)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0025)
