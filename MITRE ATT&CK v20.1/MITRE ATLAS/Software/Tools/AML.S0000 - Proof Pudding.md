# AML.S0000 - Proof Pudding

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[Proof Pudding](AML.S0000%20-%20Proof%20Pudding.md) is an open source Python tool for replicating and analyzing Proofpoint's email-scoring behavior. It trains proxy models on previously scored email text and links, predicts scores for new inputs, and identifies tokens that raise or lower predicted scores. The project includes scored datasets, pretrained models, and token-level analyses to support developing inputs intended to evade email filtering. [github](https://github.com/moohax/Proof-Pudding)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.E0002 - Silent Break Security](../../Entities/AML.E0002%20-%20Silent%20Break%20Security.md) — [Silent Break Security](../../Entities/AML.E0002%20-%20Silent%20Break%20Security.md) researchers used [Proof Pudding](AML.S0000%20-%20Proof%20Pudding.md) to train a copy-cat model of an email scoring system, identify words and URL tokens that influenced its scores, and craft emails to evade detection.

## Techniques implemented

- [AML.T0005.001 - Replicate Behavior from Model Outputs](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md) — [Proof Pudding](AML.S0000%20-%20Proof%20Pudding.md) trains proxy models using bag-of-words representations of email text and links paired with Proofpoint scores. These models approximate the target's scoring behavior and predict scores for new inputs before delivery. [github](https://github.com/moohax/Proof-Pudding)

## References

- [Proof Pudding (CVE-2019-20634) Implementation on GitHub](https://github.com/moohax/Proof-Pudding)
- [National Vulnerability Database entry for CVE-2019-20634](https://nvd.nist.gov/vuln/detail/CVE-2019-20634)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0000)
