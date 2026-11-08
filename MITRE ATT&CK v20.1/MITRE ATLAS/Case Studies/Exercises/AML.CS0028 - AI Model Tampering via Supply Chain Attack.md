# AML.CS0028 - AI Model Tampering via Supply Chain Attack

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers at Trend Micro, Inc. used service indexing portals and web searching tools to identify over 8,000 misconfigured private container registries exposed on the internet. Approximately 70% of the registries also had overly permissive access controls that allowed write access. In their analysis, the researchers found over 1,000 unique AI models embedded in private container images within these open registries that could be pulled without authentication.

This exposure could allow adversaries to download, inspect, and modify container contents, including sensitive AI model files. This is an exposure of valuable intellectual property which could be stolen by an adversary. Compromised images could also be pushed to the registry, leading to a supply chain attack, allowing malicious actors to compromise the integrity of AI models used in production systems.

**Type**  Exercise

**Target**  Private Container Registries

**Activity period**  2023-09-26

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0004 - Search Application Repositories](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0004%20-%20Search%20Application%20Repositories/README.md)

The Trend Micro researchers used service indexing portals and web searching tools to identify over 8,000 private container registries exposed on the internet. Approximately 70% of the registries had overly permissive access controls, allowing write permissions. The private container registries encompassed both independently hosted registries and registries deployed on Cloud Service Providers (CSPs). The registries were exposed due to some combination of:

- Misconfiguration leading to public access of private registry,
- Lack of proper authentication and authorization mechanisms, and/or
- Insufficient network segmentation and access controls

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

The researchers were able to exploit the misconfigured registries to pull container images without requiring authentication. In total, researchers pulled several terabytes of data containing over 20,000 images.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0007 - Discover AI Artifacts](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0007%20-%20Discover%20AI%20Artifacts/README.md)

The researchers found 1,453 unique AI models embedded in the private container images. Around half were in the Open Neural Network Exchange (ONNX) format.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0044 - Full AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0044%20-%20Full%20AI%20Model%20Access/README.md)

This gave the researchers full access to the models. Models for a variety of use cases were identified, including:

- ID Recognition
- Face Recognition
- Object Recognition
- Various Natural Language Processing Tasks

**Next**  [S04](#step-s04), [S05](#step-s05), [S06](#step-s06)

### Step S04

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.004 - AI Intellectual Property Theft](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md)

With full access to the model(s), an adversary has an organization's valuable intellectual property.

**Next**  End of path

### Step S05

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0018.000 - Poison AI Model](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md)

With full access to the model weights, an adversary could manipulate the weights to cause misclassifications or otherwise degrade performance.

**Next**  [S07](#step-s07)

### Step S06

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0018.001 - Modify AI Model Architecture](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.001%20-%20Modify%20AI%20Model%20Architecture/README.md)

With full access to the model, an adversary could modify the architecture to change the behavior.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.004 - Container Registry](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.004%20-%20Container%20Registry/README.md)

Because many of the misconfigured container registries allowed write access, the adversary's container image with the manipulated model could be pushed with the same name and tag as the original. This compromises the victim's AI supply chain, where automated CI/CD pipelines could pull the adversary's images.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0015%20-%20Evade%20AI%20Model/README.md)

Once the adversary's container image is deployed, the model may misclassify inputs due to the adversary's manipulations.

**Next**  End of path

## Attributed to

- [AML.E0011 - Trend Micro](../../Entities/AML.E0011%20-%20Trend%20Micro.md) (Security Evaluation)

## References

- [Silent Sabotage: Weaponizing AI Models in Exposed Containers](https://www.trendmicro.com/vinfo/br/security/news/cyber-attacks/silent-sabotage-weaponizing-ai-models-in-exposed-containers)
- [Exposed Container Registries: A Potential Vector for Supply-Chain Attacks](https://www.trendmicro.com/vinfo/us/security/news/virtualization-and-cloud/exposed-container-registries-a-potential-vector-for-supply-chain-attacks)
- [Mining Through Mountains of Information and Risk: Containers and Exposed Container Registries](https://www.trendmicro.com/vinfo/us/security/news/virtualization-and-cloud/mining-through-mountains-of-information-and-risk-containers-and-exposed-container-registries)
- [The Growing Threat of Unprotected Container Registries: An Urgent Call to Action](https://www.dreher.in/blog/unprotected-container-registries)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0028)
