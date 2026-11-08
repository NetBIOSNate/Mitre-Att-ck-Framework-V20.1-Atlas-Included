# AML.M0023 - Maintain an AI Bill of Materials

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Create and maintain an AI Bill of Materials (AI BOM) that identifies the components and dependencies used to build, evaluate, and operate an AI-enabled system. Include models and checkpoints, datasets, software packages, inference runtimes, container images, and agent configurations including system instructions and connected tools and data sources. For systems that use external AI services or agent tools, record the relevant providers, services, integrations, and available version identifiers.

Record component identifiers, versions, sources, suppliers or publishers, and cryptographic digests. Capture dependency and derivation relationships, such as which base model and dataset versions produced a fine-tuned model. Link to supporting provenance, integrity-verification, and evaluation records rather than treating inclusion in the AI BOM as evidence of approval or safety.

Generate or update the AI BOM when components are acquired, built, modified, or deployed. Retain version history and protect records from unauthorized modification. Identify gaps where upstream information or hosted-service version details are unavailable.

Use the AI BOM to assess component changes, correlate security advisories and reports of compromised artifacts with deployed systems, and trace affected dependencies and derived models. Use these findings to prioritize investigation, replacement, rollback, or retraining.

An AI BOM provides inventory and traceability. It does not establish that a listed component is authentic, unmodified, or free of malicious behavior. Combine it with [Verify AI Artifacts](AML.M0014%20-%20Verify%20AI%20Artifacts.md), [Maintain AI Dataset Provenance](AML.M0025%20-%20Maintain%20AI%20Dataset%20Provenance.md), and [Validate AI Model](AML.M0008%20-%20Validate%20AI%20Model.md).

**Mitigation categories**  Policy

**Lifecycle phases**  Data Preparation, AI Model Engineering, AI Model Evaluation, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0010 - Supply Chain Compromise](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md) — Record component identities, versions, sources, and dependencies across the AI supply chain. Use these records to identify builds and deployments affected by reported compromises and guide replacement or rollback.
- [AML.T0010.001 - Software](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.001%20-%20Software/README.md) — Record AI software packages, frameworks, inference engines, and DevOps tools, including versions and dependencies. Use these records to identify deployments affected by reported software compromises and guide replacement or rollback.
- [AML.T0010.002 - Data Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.002%20-%20Data%20Repository/README.md) — Record dataset sources, releases, and relationships to training, evaluation, and retrieval workflows. Use these records to identify systems exposed to compromised sources or releases and trace downstream effects.
- [AML.T0010.003 - Model Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md) — Record model publishers, repositories, versions, available digests, and bundled components. Use these records to trace compromised releases to fine-tuned derivatives and consuming applications and guide investigation, replacement, or rollback.
- [AML.T0010.004 - Container Registry](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.004%20-%20Container%20Registry/README.md) — Record container image digests, registries, included AI components, and consuming workloads. Use these records to identify deployments running compromised images.
- [AML.T0010.005 - AI Agent Tool](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.005%20-%20AI%20Agent%20Tool/README.md) — Record agent tool packages and remote integrations, including providers, available versions, endpoints, and consuming agents. Use these records to identify agents exposed to compromised tools and guide disabling, replacement, or reconnection to a safe version.
- [AML.T0018.000 - Poison AI Model](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) — Record relationships between base models, checkpoints, fine-tuned derivatives, and deployed applications. Use these records to trace poisoned model versions to potentially affected derivatives and deployments and guide evaluation, replacement, or retraining.
- [AML.T0020 - Training Data Poisoning](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md) — Record training and fine-tuning dataset identities, versions, and relationships to derived models and deployed applications. Use these records to trace poisoned data to affected models and applications and guide dataset replacement, model reevaluation, or retraining.
- [AML.T0109 - AI Supply Chain Rug Pull](../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0109%20-%20AI%20Supply%20Chain%20Rug%20Pull/README.md) — Retain versioned component and dependency records across updates. Use these records to identify deployments that adopted a subsequently identified malicious release and guide replacement or rollback.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0023)
