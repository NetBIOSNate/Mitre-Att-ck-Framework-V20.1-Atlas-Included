# AML.T0096 - AI Service API

[MITRE ATLAS](../../../README.md) / [AML.TA0014 - Command and Control](../README.md)

Adversaries may communicate using the API of an AI service on the victim's system. The adversary's commands to the victim system, and often the results, are embedded in the normal traffic of the AI service.

An AI service API command and control channel is covert because the adversary's commands blend in with normal communications, so an adversary may use this technique to avoid detection. Using existing infrastructure on the victim's system allows the adversary to live off the land, further reducing their footprint.

AI service APIs may be abused as C2 channels when an adversary wants to be stealthy and maintain long-term persistence for espionage activities  [microsoft](https://www.microsoft.com/en-us/security/blog/2025/11/03/sesameop-novel-backdoor-uses-openai-assistants-api-for-command-and-control/).

**Tactics**  [AML.TA0014 - Command and Control](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0042 - SesameOp: Novel backdoor uses OpenAI Assistants API for command and control](../../../Case%20Studies/Incidents/AML.CS0042%20-%20SesameOp%20-%20Novel%20backdoor%20uses%20OpenAI%20Assistants%20API%20for%20command%20and%20control.md) · [S00](../../../Case%20Studies/Incidents/AML.CS0042%20-%20SesameOp%20-%20Novel%20backdoor%20uses%20OpenAI%20Assistants%20API%20for%20command%20and%20control.md#step-s00)

## Mitigations

- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Authenticate AI service API callers and monitor queries for policy violations and misuse.

## Software implementations

- [AML.S0016 - SesameOp](../../../Software/Malware/AML.S0016%20-%20SesameOp.md) — [SesameOp](../../../Software/Malware/AML.S0016%20-%20SesameOp.md) uses Assistant objects, threads, and messages in the OpenAI Assistants API as a command-and-control channel. It retrieves encrypted payloads from messages, executes the decrypted instructions locally, and posts compressed, encrypted execution results as new messages for the operator to retrieve. [source-1](https://www.microsoft.com/en-us/security/blog/2025/11/03/sesameop-novel-backdoor-uses-openai-assistants-api-for-command-and-control/)

## References

- [SesameOp: Novel backdoor uses OpenAI Assistants API for command and control | Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2025/11/03/sesameop-novel-backdoor-uses-openai-assistants-api-for-command-and-control/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0096)
