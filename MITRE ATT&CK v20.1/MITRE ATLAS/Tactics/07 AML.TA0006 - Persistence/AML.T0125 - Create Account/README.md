# AML.T0125 - Create Account

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may create an account to maintain access to an AI system or its supporting infrastructure. With a sufficient level of access, creating such accounts may be used to establish secondary credentialed access that do not require persistent remote access tools to be deployed on the system.

Accounts may be created on local systems, in enterprise domains, cloud tenants, identity providers, or individual services. In AI environments, adversaries may create user, service, workload, or automation accounts in AI platforms, model or dataset repositories, development environments, experiment trackers, orchestration services, data stores, and other AI operations infrastructure.

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1136](../../../../Enterprise/Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/README.md) · [MITRE ATT&CK T1136](https://attack.mitre.org/techniques/T1136/)

## Case studies

- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S16](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s16)

## Mitigations

- [AML.M0043 - AI Agent External Resource Lifecycle Management](../../../Mitigations/AML.M0043%20-%20AI%20Agent%20External%20Resource%20Lifecycle%20Management.md) — Disable or delete agent-created accounts when authorization ends to limit persistent access through those accounts.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0125)
