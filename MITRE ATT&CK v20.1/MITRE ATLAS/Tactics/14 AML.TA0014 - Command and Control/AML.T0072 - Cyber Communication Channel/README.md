# AML.T0072 - Cyber Communication Channel

[MITRE ATLAS](../../../README.md) / [AML.TA0014 - Command and Control](../README.md)

Adversaries may establish or use cyber communication channels for command and control. A channel may use any network protocol, service, repository, relay, or other intermediary and may operate synchronously or asynchronously.

See the ATT&CK [Command and Control](https://attack.mitre.org/tactics/TA0011/) tactic for techniques describing specific protocols, services, relays, tunneling methods, and communication patterns.

**Tactics**  [AML.TA0014 - Command and Control](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0027 - Organization Confusion on Hugging Face](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s09)
- [AML.CS0031 - Malicious Models on Hugging Face](../../../Case%20Studies/Incidents/AML.CS0031%20-%20Malicious%20Models%20on%20Hugging%20Face.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0031%20-%20Malicious%20Models%20on%20Hugging%20Face.md#step-s05)
- [AML.CS0052 - LLMSmith: RCE Vulnerabilities in LLM-Integrated Applications](../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md) · [S10](../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md#step-s10)
- [AML.CS0065 - Model Namespace Reuse Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md#step-s07)
- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S13](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s13)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S17](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s17), [S35](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s35)

## Mitigations

- [AML.M0043 - AI Agent External Resource Lifecycle Management](../../../Mitigations/AML.M0043%20-%20AI%20Agent%20External%20Resource%20Lifecycle%20Management.md) — Disable agent-created communication infrastructure when authorization ends to disrupt persistent command-and-control channels.

## Software implementations

- [AML.S0010 - Sliver](../../../Software/Tools/AML.S0010%20-%20Sliver.md) — [Sliver](../../../Software/Tools/AML.S0010%20-%20Sliver.md) implants launched through TensorFlow/Keras model execution established remote sessions that allowed the researcher to execute commands and explore the host environment. [source-1](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0072)
