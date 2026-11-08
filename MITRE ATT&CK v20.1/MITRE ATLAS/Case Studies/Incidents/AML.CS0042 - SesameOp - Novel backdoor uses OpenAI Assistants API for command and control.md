# AML.CS0042 - SesameOp: Novel backdoor uses OpenAI Assistants API for command and control

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

The Microsoft Incident Response - Detection and Response Team (DART) investigated a compromised system where a threat actor utilized SesameOp, a backdoor implant that abuses the OpenAI Assistants API as a covert command and control channel, for espionage activities. The SesameOp malware used the OpenAI API to fetch and execute the threat actor's commands and to exfiltrate encrypted results from the victim system.

The threat actor had maintained a presence on the compromised system for several months. They had control of multiple internal web shells which executed commands from malicious processes that relied on compromised Visual Studio utilities. Investigation of other Visual Studio utilities led to the discovery of the novel SesameOp backdoor.

**Type**  Incident

**Actor**  Unknown Threat Actor

**Target**  OpenAI Assistants API

**Reporter**  Microsoft Incident Response - Detection and Response Team (DART)

**Activity period**  2025-07

## Procedure steps

### Step S00

[AML.TA0014 - Command and Control](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/README.md) / [AML.T0096 - AI Service API](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0096%20-%20AI%20Service%20API/README.md)

The threat actor abused the OpenAI Assistants API to relay commands to the SesameOp malware, which executed them on the victim system, and sent the results back to the threat actor via the same channel. Both commands and results are encrypted.

SesameOp cleaned up its tracks by deleting the Assistants and Messages it created and used for communication.

**Next**  End of path

## Uses

- [AML.S0016 - SesameOp](../../Software/Malware/AML.S0016%20-%20SesameOp.md) — The threat actor deployed [SesameOp](../../Software/Malware/AML.S0016%20-%20SesameOp.md) in a compromised environment to maintain remote access for espionage. The backdoor retrieved operator instructions through the OpenAI Assistants API, executed them on the compromised host, and returned encrypted results through the same service. [ref-1](https://www.microsoft.com/en-us/security/blog/2025/11/03/sesameop-novel-backdoor-uses-openai-assistants-api-for-command-and-control/)

## References

- [SesameOp: Novel backdoor uses OpenAI Assistants API for command and control](https://www.microsoft.com/en-us/security/blog/2025/11/03/sesameop-novel-backdoor-uses-openai-assistants-api-for-command-and-control/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0042)
