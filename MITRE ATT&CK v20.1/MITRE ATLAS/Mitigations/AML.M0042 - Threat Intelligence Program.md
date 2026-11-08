# AML.M0042 - Threat Intelligence Program

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

A Threat Intelligence Program enables organizations to proactively collect, analyze, and share information on threats to AI and cyber systems by leveraging internal observations and external reporting. The program supports decision-making processes, prioritizes defenses, and improves incident response by delivering actionable intelligence tailored to the organization's risk profile and operational environment.

This mitigation can be implemented through the following measures:

**Establish an AI Threat Intelligence Team and Define and Requirements**
- Assign personnel to collect, analyze, and act on intelligence related to threats targeting AI systems.
- Coordinate across cybersecurity, AI/ML development, and model evaluation teams to translate intelligence into actionable defenses.
- Define intelligence requirements around critical AI assets, dependencies, deployment environments, and the decisions intelligence must support.
- Prioritize collection according to relevant adversary objectives, capabilities, access requirements, and potential operational impacts. Include threats to AI components and the software, services, and infrastructure supporting them.

**Collect and Automate AI Threat Intelligence**
- Collect intelligence from internal sources, including AI application logs, model monitoring, red-team exercises, security incidents, and adversarial testing.
- Monitor external sources, including AI vulnerability disclosures, incident reports, security research, and threat intelligence feeds.
- Track active campaigns and adversary capabilities, including autonomous agent campaigns, reported use of zero-day vulnerabilities, and impersonation campaigns.
- Collect information on compromised supply chains and published poisoned datasets, models, and AI agent tools.
- Use threat intelligence platforms (TIPs) to aggregate, enrich, and disseminate AI-related threat intelligence.
- Integrate intelligence with SIEMs and AI monitoring tools to correlate indicators of compromise with internal events.

**Analyze and Operationalize Intelligence**
- Map emerging and observed threats to MITRE ATLAS tactics and techniques to understand adversary behaviors and potential impacts.
- Assess applicability to deployed components, versions, configurations, and workflows, including the access and conditions required for an attack.
- Prioritize defensive actions based on threat relevance, AI system criticality, and potential operational impact.
- Use intelligence to identify affected systems and artifacts, prioritize remediation or compensating controls, and update threat models, adversarial evaluations, detection logic, and incident response procedures.
- Correlate relevant indicators and behaviors with internal telemetry to identify related activity. Validate detection logic against the organization's environment and available observations.
- Assign defensive actions to responsible owners, track their completion, and verify whether they address the identified exposure.

**Share Intelligence and Continuously Improve**
- Share AI threat intelligence, attack patterns, and lessons learned with trusted industry partners and AI security communities.
- Regularly update intelligence priorities as AI capabilities, vulnerabilities, and adversarial techniques evolve.
- Evaluate program effectiveness based on improvements in threat detection, defensive coverage, and incident re
sponse.

**Tools and Resources for Implementation**
- Threat Knowledge Bases and Intelligence Sources
  - MITRE ATLAS: Organize intelligence around documented adversary behaviors.
  - Vendor advisories, CVE/NVD, and CISA's Known Exploited Vulnerabilities Catalog: Identify vulnerabilities affecting deployed components.
  - Supplier and repository security reporting: Identify compromised models, datasets, packages, containers, and AI agent tools.
  - Incident reports and security research: Assess targeting and attack methods, distinguishing operational activity from research demonstrations.
- Intelligence Management and Sharing
  - Threat intelligence platforms, such as OpenCTI and MISP: Organize and share indicators, relationships, sources, and confidence assessments.
  - STIX and TAXII: Support structured intelligence exchange between compatible systems.
  - Case-management systems: Track investigations, assigned defensive actions, and outcomes.
- Operational Analysis and Validation
  - SIEMs and AI monitoring tools: Correlate intelligence with internal telemetry to investigate related activity.
  - Asset and dependency inventories: Identify exposure to reported vulnerabilities and compromised artifacts.
  - Security evaluation capabilities: Turn intelligence into system-specific tests using appropriate manual and automated methods.
- Community and Collaboration
  - ISACs and AI security communities: Exchange relevant campaign observations and defensive findings.
  - Supplier and platform reporting channels: Report malicious artifacts and compromised services to support investigation and removal.

**ATT&CK mapping**  [Local ATT&CK M1019](../../Enterprise/Defenses/Mitigations/M1019%20-%20Threat%20Intelligence%20Program.md) · [MITRE ATT&CK M1019](https://attack.mitre.org/mitigations/M1019/)

**Mitigation categories**  Policy

**Lifecycle phases**  Business and Data Understanding, Data Preparation, AI Model Engineering, AI Model Evaluation, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0010 - Supply Chain Compromise](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md) — Collect, analyze, and share intelligence on compromised suppliers, components, and distribution channels. Use this intelligence to identify affected dependencies, prevent their introduction into downstream systems, and prioritize investigation and replacement of compromised components.
- [AML.T0010.000 - Hardware](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.000%20-%20Hardware/README.md) — Collect, analyze, and share intelligence on compromised hardware suppliers and products, including affected models and production batches where known. Use this intelligence to identify affected hardware, prevent its introduction into downstream systems, and prioritize investigation and replacement.
- [AML.T0010.001 - Software](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.001%20-%20Software/README.md) — Collect, analyze, and share intelligence on compromised software packages, dependencies, and releases, including affected versions and distribution locations. Use this intelligence to identify affected software, prevent its introduction into downstream systems, and prioritize investigation and replacement.
- [AML.T0010.002 - Data Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.002%20-%20Data%20Repository/README.md) — Collect, analyze, and share intelligence on data repositories and distribution services delivering compromised datasets, including affected publishing accounts, dataset versions, and references. Use this intelligence to identify affected data dependencies, prevent ingestion of compromised datasets, and prioritize investigation of workflows that have already consumed them.
- [AML.T0010.003 - Model Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md) — Collect, analyze, and share intelligence on model repositories and distribution services delivering compromised models, including affected publishing accounts, model versions, and references. Use this intelligence to identify affected model dependencies, prevent integration of compromised models, and prioritize investigation of systems that have already incorporated them.
- [AML.T0010.004 - Container Registry](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.004%20-%20Container%20Registry/README.md) — Collect, analyze, and share intelligence on container registries distributing compromised images, including affected repositories, tags, and image digests. Use this intelligence to identify affected image dependencies, prevent deployment of compromised images, and prioritize investigation and replacement of affected containers.
- [AML.T0010.005 - AI Agent Tool](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.005%20-%20AI%20Agent%20Tool/README.md) — Collect, analyze, and share intelligence on compromised AI agent tool dependencies, including affected packages, versions, and remote services. Use this intelligence to identify affected integrations, prevent adoption of compromised tools, and prioritize disabling affected integrations and investigating prior tool activity.
- [AML.T0017.001 - Autonomous Exploit Development](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.001%20-%20Autonomous%20Exploit%20Development/README.md) — Collect, analyze, and share intelligence on adversary use of autonomous agents to develop exploits, including targeted software, identified vulnerabilities, and reported exploit capabilities. Use this intelligence to identify exposed systems, prioritize remediation and compensating controls, and update adversarial evaluations and detection procedures.
- [AML.T0049 - Exploit Public-Facing Application](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md) — Collect, analyze, and share intelligence on adversary use of exploits, including zero-day vulnerabilities, against public-facing applications. Use this intelligence to identify exposed applications, prioritize remediation and compensating controls, and update detection and response procedures.
- [AML.T0073 - Impersonation](../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0073%20-%20Impersonation/README.md) — Collect, analyze, and share intelligence on impersonation campaigns, including claimed identities, fabricated personas, lures, and associated infrastructure. Use this intelligence to help personnel and system operators recognize deceptive requests, strengthen identity verification procedures, and investigate related activity across human and AI agent interactions.
- [AML.T0106 - Exploitation for Credential Access](../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0106%20-%20Exploitation%20for%20Credential%20Access/README.md) — Collect, analyze, and share intelligence on adversary use of exploits, including zero-day vulnerabilities, to obtain credentials. Use this intelligence to identify exposed systems, prioritize remediation and compensating controls, and update detection and response procedures.
- [AML.T0107 - Exploitation for Defense Evasion](../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0107%20-%20Exploitation%20for%20Defense%20Evasion/README.md) — Collect, analyze, and share intelligence on adversary use of exploits, including zero-day vulnerabilities, to bypass security features. Use this intelligence to identify exposed systems, prioritize remediation and compensating controls, and update detection and response procedures.
- [AML.T0115 - Publish Poisoned AI Artifacts](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/README.md) — Collect, analyze, and share intelligence on published poisoned AI artifacts, including identifiers, versions, distribution locations, and evidence of malicious content or behavior. Use this intelligence to block acquisition and use of identified artifacts, investigate existing exposure, and support reporting to distribution platforms for removal.
- [AML.T0115.000 - Datasets](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.000%20-%20Datasets/README.md) — Collect, analyze, and share intelligence on published poisoned datasets, including identifiers, versions, distribution locations, and evidence of manipulated samples, labels, annotations, or metadata. Use this intelligence to block acquisition and use of identified datasets, investigate training workflows and models that have consumed them, and support reporting to distribution platforms for removal.
- [AML.T0115.001 - Models](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.001%20-%20Models/README.md) — Collect, analyze, and share intelligence on published poisoned models, including identifiers, versions, distribution locations, and evidence of malicious content or behavior. Use this intelligence to block acquisition and use of identified models, investigate systems that have loaded or incorporated them, and support reporting to distribution platforms for removal.
- [AML.T0115.002 - AI Agent Tools](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.002%20-%20AI%20Agent%20Tools/README.md) — Collect, analyze, and share intelligence on published poisoned AI agent tools, including package or service identifiers, versions, distribution locations, and evidence of malicious content or behavior. Use this intelligence to block installation or connection to identified tools, investigate agents that have used them, and support reporting to distribution platforms or service providers for removal.
- [AML.T0116 - Autonomous Reconnaissance](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md) — Collect, analyze, and share intelligence on autonomous reconnaissance campaigns, including targeting, infrastructure, and observed sequences of investigative actions. Use this intelligence to correlate related reconnaissance activity, identify assets receiving adversary attention, and prioritize monitoring and exposure reduction.
- [AML.T0117 - Autonomous Attack-Path Adaptation](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md) — Collect, analyze, and share intelligence on observed autonomous cyber behaviors, including observed changes in objectives and techniques following failed attempts, defensive responses, or newly acquired access. Use this intelligence to identify alternative attack paths requiring protection, update defensive evaluations, and prepare response procedures for continued activity after an initial path is blocked.
- [AML.T0119 - Exploit Automated Artifact Processing Pipeline](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0119%20-%20Exploit%20Automated%20Artifact%20Processing%20Pipeline/README.md) — Collect, analyze, and share intelligence on adversary use of crafted artifacts to exploit automated processing pipelines. Use this intelligence to identify exposed processing workflows, prioritize remediation and compensating controls, and update detection and response procedures.
- [AML.T0122 - Exploitation of Remote Services](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0122%20-%20Exploitation%20of%20Remote%20Services/README.md) — Collect, analyze, and share intelligence on adversary use of exploits, including zero-day vulnerabilities, against remote services. Use this intelligence to identify exposed services and reachable attack paths, prioritize remediation and compensating controls, and update detection and response procedures.
- [AML.T0124 - Autonomous Attack Orchestration](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md) — Collect, analyze, and share intelligence on autonomously orchestrated campaigns, including infrastructure, task allocation, and coordination among agents. Use this intelligence to correlate distributed activity as part of a common operation, identify coordination dependencies, and coordinate containment across affected systems.
- [AML.T0140 - Centralized AI Service Request Routing](../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md) — Collect, analyze, and share intelligence on coordinated AI service requests distributed across accounts, providers, and intermediary services. Use this intelligence to correlate activity across access pathways, identify shared routing infrastructure, and coordinate detection and response to campaigns whose scale and common control may be obscured within individual accounts or services.

## References

- [NIST SP 800-150: Guide to Cyber Threat Information Sharing](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-150.pdf)
- [Code of Practice for the Cyber Security of AI](https://www.gov.uk/government/publications/ai-cyber-security-code-of-practice/code-of-practice-for-the-cyber-security-of-ai)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0042)
