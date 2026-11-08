# AML.T0105 - Escape to Host

[MITRE ATLAS](../../../README.md) / [AML.TA0012 - Privilege Escalation](../README.md)

Adversaries may break out of a container or virtualized environment to gain access to the underlying host. This can allow an adversary access to other containerized or virtualized resources from the host level or to the host itself. In principle, containerized / virtualized resources should provide a clear separation of application functionality and be isolated from the host environment.

There are many ways an adversary may escape from a container or sandbox environment via AI Systems. For example, modifying an AI Agent's configuration to disable safety features or user confirmations could allow the adversary to invoke tools to be run on host environments rather than in the sandbox.

**Tactics**  [AML.TA0012 - Privilege Escalation](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1611](../../../../Enterprise/Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1611%20-%20Escape%20to%20Host/README.md) · [MITRE ATT&CK T1611](https://attack.mitre.org/techniques/T1611/)

## Case studies

- [AML.CS0050 - OpenClaw 1-Click Remote Code Execution](../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md#step-s07)
- [AML.CS0052 - LLMSmith: RCE Vulnerabilities in LLM-Integrated Applications](../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md#step-s09)
- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S31](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s31)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0105)
