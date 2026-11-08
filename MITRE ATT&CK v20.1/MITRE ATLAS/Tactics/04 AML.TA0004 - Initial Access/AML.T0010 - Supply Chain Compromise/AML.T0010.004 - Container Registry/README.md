# AML.T0010.004 - Container Registry

[MITRE ATLAS](../../../../README.md) / [AML.TA0004 - Initial Access](../../README.md) / [AML.T0010 - Supply Chain Compromise](../README.md)

An adversary may compromise a victim's container registry by pushing a manipulated container image and overwriting an existing container name and/or tag. Users of the container registry as well as automated CI/CD pipelines may pull the adversary's container image, compromising their AI Supply Chain. This can affect development and deployment environments.

Container images may include AI models, so the compromised image could have an AI model which was manipulated by the adversary (See [Manipulate AI Model](../../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/README.md)).

**Tactics**  [AML.TA0004 - Initial Access](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0028 - AI Model Tampering via Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md#step-s07)

## Mitigations

- [AML.M0014 - Verify AI Artifacts](../../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Pin container images to approved digests and verify their authenticity before deployment. Reject substitutions introduced through mutable image tags.
- [AML.M0023 - Maintain an AI Bill of Materials](../../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Record container image digests, registries, included AI components, and consuming workloads. Use these records to identify deployments running compromised images.
- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on container registries distributing compromised images, including affected repositories, tags, and image digests. Use this intelligence to identify affected image dependencies, prevent deployment of compromised images, and prioritize investigation and replacement of affected containers.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0010.004)
