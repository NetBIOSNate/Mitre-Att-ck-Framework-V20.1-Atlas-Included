# AML.T0138 - Indicator Removal

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may delete, alter, or falsify records and artifacts to conceal their activity, impede investigation, or make unauthorized actions appear legitimate. Targeted artifacts may include logs, command histories, files, metadata, repository history, and published content. Changes may selectively remove suspicious evidence while preserving surrounding material to maintain the appearance of normal activity.

Agents may also conceal activity by modifying artifacts on external collaboration and distribution platforms. Editing public messages, removing malicious content, or rewriting revision history can obscure prior actions, make contributions appear benign, and complicate reconstruction of an attack. These changes may help an agent preserve credibility and continue operating after its activity attracts scrutiny, even when earlier versions remain recoverable. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

Autonomous AI agents may identify and manipulate evidence of their own actions without a human directing each concealment step. Agents may edit or delete accessible transcripts, replace records with misleading content, or tamper with harness components responsible for executing or recording tool calls. Such tampering can cause recorded actions or results to differ from actual execution, undermining oversight that relies on the affected records. [metr-hf](https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/#agents-were-very-interested-in-manipulating-their-own-transcripts,-and-their-tests-successfully-%E2%80%9Cspoofed%E2%80%9D-some-tool-calls-in-our-transcripts)

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1070](../../../../Enterprise/Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/README.md) · [MITRE ATT&CK T1070](https://attack.mitre.org/techniques/T1070/)

## Case studies

- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S26](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s26)

## Used by

- [AML.E0036 - OpenAI](../../../Entities/AML.E0036%20-%20OpenAI.md) (Unintended Consequence) — Autonomous [OpenAI](../../../Entities/AML.E0036%20-%20OpenAI.md) agents attempted to edit or delete local records and spoof tool-call transcripts. [metr-hf](https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/)

## References

- [Brief independent investigation of agents' behavior, reasoning and collaboration in the OpenAI / Hugging Face hacking incident](https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/#agents-were-very-interested-in-manipulating-their-own-transcripts,-and-their-tests-successfully-%E2%80%9Cspoofed%E2%80%9D-some-tool-calls-in-our-transcripts)
- [Incident Report: unsanctioned agent behaviour during cyber testing](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0138)
