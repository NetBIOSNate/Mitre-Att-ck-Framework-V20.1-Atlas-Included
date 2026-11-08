# AML.T0073 - Impersonation

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may impersonate an existing person or organization, trusted AI agent, or present a fabricated persona as a trustworthy or independent party, to persuade a target to act on their behalf. Claimed identities may include authority figures, colleagues, service providers, software contributors, independent experts, or other users on shared platforms. Fabricated personas can establish apparent credibility even when the identity has no prior relationship with the target.

Adversaries may communicate with victims through [Phishing](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md) or [Spearphishing via Social Engineering LLM](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/AML.T0052.000%20-%20Spearphishing%20via%20Social%20Engineering%20LLM/README.md), leveraging the claimed identity to obtain sensitive information, induce execution, gain access, or secure approval of a malicious change. They may target resources that are part of the AI DevOps lifecycle, such as model repositories, container registries, and software registries.

Adversaries may impersonate a trusted AI agent or service when communicating with automated systems. They may present an adversary-controlled endpoint using a trusted peer's name, identifier, metadata, or claimed role, causing another agent or service to treat the endpoint's messages or requests as originating from that peer. [agent-name-collision](https://arxiv.org/abs/2609.27624)

Autonomous AI agents may create and maintain personas without a human specifying each identity or interaction. Multiple controlled personas may be presented as independent contributors or reviewers, concealing their common control and creating the appearance that separate parties have verified or endorsed a claim, artifact, or requested action. An agent may coordinate the personas' content and response timing to make their interactions appear unrelated and reuse those personas across communication channels. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

Impersonation content may also be embedded in artifacts intended for automated consumers. For example, an adversary or AI agent may plant output falsely attributed to a maintainer or CI system that claims a software change has been approved and directs another AI agent to merge or release it. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1684.001](../../../../Enterprise/Tactics/07%20TA0005%20-%20Stealth/T1684%20-%20Social%20Engineering/T1684.001%20-%20Impersonation/README.md) · [MITRE ATT&CK T1684.001](https://attack.mitre.org/techniques/T1684/001/)

## Case studies

- [AML.CS0027 - Organization Confusion on Hugging Face](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s01)
- [AML.CS0033 - Live Deepfake Image Injection to Evade Mobile KYC Verification](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md#step-s08)
- [AML.CS0034 - ProKYC: Deepfake Tool for Account Fraud Attacks](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md) · [S07](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md#step-s07)
- [AML.CS0044 - LAMEHUG: Malware Leveraging Dynamic AI-Generated Commands](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md#step-s02)
- [AML.CS0053 - Poisoned Postmark MCP Server Email Exfiltration](../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md) · [S00](../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md#step-s00)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S24](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s24)

## Mitigations

- [AML.M0042 - Threat Intelligence Program](../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on impersonation campaigns, including claimed identities, fabricated personas, lures, and associated infrastructure. Use this intelligence to help personnel and system operators recognize deceptive requests, strengthen identity verification procedures, and investigate related activity across human and AI agent interactions.

## References

- [Incident Report: unsanctioned agent behaviour during cyber testing](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)
- [Agent Name Collision Attacks in Multi-Agent Systems](https://arxiv.org/abs/2609.27624)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0073)
