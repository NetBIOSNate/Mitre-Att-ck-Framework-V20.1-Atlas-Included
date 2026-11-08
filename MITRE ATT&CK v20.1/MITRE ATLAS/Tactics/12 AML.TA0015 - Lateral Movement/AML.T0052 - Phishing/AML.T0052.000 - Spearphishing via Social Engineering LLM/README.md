# AML.T0052.000 - Spearphishing via Social Engineering LLM

[MITRE ATLAS](../../../../README.md) / [AML.TA0015 - Lateral Movement](../../README.md) / [AML.T0052 - Phishing](../README.md)

Adversaries may use large language models (LLMs) or LLM-based AI agents to conduct targeted social engineering through electronically delivered messages and conversations. The model may generate content for an operator to deliver, or in the case of an AI agent connected to communication tools, it may autonomously select recipients, develop pretexts, send messages, and manage follow-up interactions. Objectives may include inducing a target to disclose sensitive information, execute malicious content, grant access, or approve a software change that enables compromise.

AI agents may select and conduct spearphishing without a human prescribing the social engineering approach or directing each interaction. This behavior may also arise while an agent pursues an initially legitimate objective, if its selected methods cross authorization or trust boundaries. An agent may use information gathered about a target to tailor its language, persona, and requests, then adapt subsequent messages based on replies and other observations. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

Communications may occur through email, code-hosting or messaging platforms, file-transfer notifications, or other services that reach selected individuals. AI agents may sustain interactions across channels, deliver malicious files or links, and follow up with requests intended to induce execution or approval. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

An AI agent may coordinate communications across multiple controlled identities, tailoring their content and timing to appear independent. Supporting messages may endorse a malicious contribution, challenge a security warning, or pressure a recipient to approve or execute content. This false corroboration can support a sustained persuasion attempt rather than a single generated message. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

**Tactics**  [AML.TA0004 - Initial Access](../../../04%20AML.TA0004%20-%20Initial%20Access/README.md), [AML.TA0015 - Lateral Movement](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0020 - Indirect Prompt Injection Threats: Bing Chat Data Pirate](../../../../Case%20Studies/Exercises/AML.CS0020%20-%20Indirect%20Prompt%20Injection%20Threats%20-%20Bing%20Chat%20Data%20Pirate.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0020%20-%20Indirect%20Prompt%20Injection%20Threats%20-%20Bing%20Chat%20Data%20Pirate.md#step-s03)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S12](../../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s12)

## Mitigations

- [AML.M0018 - User Training](../../../../Mitigations/AML.M0018%20-%20User%20Training.md) — Train users to identify phishing attempts and understand that AI can be used to generate targeted and convincing messages.
- [AML.M0034 - Deepfake Detection](../../../../Mitigations/AML.M0034%20-%20Deepfake%20Detection.md) — Deepfake detection can be used to identify and block phishing attempts that use generated content.

## Software implementations

- [AML.S0018 - Xanthorox](../../../../Software/Tools/AML.S0018%20-%20Xanthorox.md) — [Xanthorox](../../../../Software/Tools/AML.S0018%20-%20Xanthorox.md) was marketed as supporting phishing campaign development using integrated AI products and services. [source-1](https://cloud.google.com/blog/topics/threat-intelligence/distillation-experimentation-integration-ai-adversarial-use)

## References

- [Incident Report: unsanctioned agent behaviour during cyber testing](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0052.000)
