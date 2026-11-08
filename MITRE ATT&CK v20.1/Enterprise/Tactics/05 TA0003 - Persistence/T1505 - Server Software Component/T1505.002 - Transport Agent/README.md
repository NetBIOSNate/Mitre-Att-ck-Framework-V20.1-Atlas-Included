# T1505.002 - Transport Agent

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1505 - Server Software Component](../README.md)

Adversaries may abuse Microsoft transport agents to establish persistent access to systems. Microsoft Exchange transport agents can operate on email messages passing through the transport pipeline to perform various tasks such as filtering spam, filtering malicious attachments, journaling, or adding a corporate signature to the end of all outgoing emails.(Citation: Microsoft TransportAgent Jun 2016)(Citation: ESET LightNeuron May 2019) Transport agents can be written by application developers and then compiled to .NET assemblies that are subsequently registered with the Exchange server. Transport agents will be invoked during a specified stage of email processing and carry out developer defined tasks. 

Adversaries may register a malicious transport agent to provide a persistence mechanism in Exchange Server that can be triggered by adversary-specified email events.(Citation: ESET LightNeuron May 2019) Though a malicious transport agent may be invoked for all emails passing through the Exchange transport pipeline, the agent can be configured to only carry out specific tasks in response to adversary defined criteria. For example, the transport agent may only carry out an action like copying in-transit attachments and saving them for later exfiltration if the recipient email address matches an entry on a list provided by the adversary.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1505/002)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Regularly check component software on critical services that adversaries may target for persistence to verify the integrity of the systems and identify if unexpected changes have been made.
- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Ensure all application component binaries are signed by the correct application developers.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow administrator accounts that have permissions to add component software on these services to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.

## Detection strategies

- [DET0166 - Detection Strategy for T1505.002 - Transport Agent Abuse (Windows/Linux)](../../../../Defenses/Detection%20Strategies/DET0166%20-%20Detection%20Strategy%20for%20T1505.002%20-%20Transport%20Agent%20Abuse%20%28Windows%20-%20Linux%29.md)

## Procedure examples

- [S0395 - LightNeuron](../../../../Threat%20Intelligence/Software/Malware/S0395%20-%20LightNeuron.md) — [LightNeuron](https://attack.mitre.org/software/S0395) has used a malicious Microsoft Exchange transport agent for persistence.(Citation: ESET LightNeuron May 2019) [ESET LightNeuron May 2019](https://www.welivesecurity.com/wp-content/uploads/2019/05/ESET-LightNeuron.pdf)

## Sources

- [Microsoft TransportAgent Jun 2016](https://docs.microsoft.com/en-us/exchange/transport-agents-exchange-2013-help)
- [ESET LightNeuron May 2019](https://www.welivesecurity.com/wp-content/uploads/2019/05/ESET-LightNeuron.pdf)
