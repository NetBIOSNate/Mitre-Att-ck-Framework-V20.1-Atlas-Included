# AML.T0142 - Event Triggered Execution

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may establish persistence by creating or modifying event handlers, startup hooks, or associated configuration so that subsequent system or application activity automatically executes adversary-controlled code or commands. Triggers may include interpreter initialization, application execution, or other events processed by the affected mechanism. These modifications can allow malicious behavior to recur without another direct execution request from the adversary.

In AI environments, adversaries may target hooks in the software and execution environments used for data processing, model training, evaluation, inference, or agent tool execution. For example, Python startup hooks may execute adversary-controlled code when a subsequent workflow or tool invocation starts an interpreter that processes the hook. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing) 

Triggered code may perform malicious actions directly or emit content that is subsequently consumed by an AI system. Such content may contain fabricated approvals or instructions intended to manipulate the system's later behavior or make normally unobservable information available. AI Agents may also place triggers or trip-wires behind to observe, act on, or report conditions that the agent can no longer reach or are beyond its execution window. [metr](https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/##extracting-information-about-the-scorer-from-trip-wires)

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1546](../../../../Enterprise/Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/README.md) · [MITRE ATT&CK T1546](https://attack.mitre.org/techniques/T1546/)

## Case studies

- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S23](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s23)

## Mitigations

- [AML.M0011 - Restrict Library Loading](../../../Mitigations/AML.M0011%20-%20Restrict%20Library%20Loading.md) — Restrict automatic loading to trusted locations and disable unnecessary interpreter startup hooks.
- [AML.M0013 - Code Signing](../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Enforce that all software packages be signed before execution.

## References

- [Incident Report: unsanctioned agent behaviour during cyber testing](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)
- [Brief independent investigation of agents' behavior, reasoning and collaboration in the OpenAI / Hugging Face hacking incident](https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/##extracting-information-about-the-scorer-from-trip-wires)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0142)
