# AML.T0090 - OS Credential Dumping

[MITRE ATLAS](../../../README.md) / [AML.TA0013 - Credential Access](../README.md)

Adversaries may extract credentials from OS caches, application memory, or other sources on a compromised system. Credentials are often in the form of a hash or clear text, and can include usernames and passwords, application tokens, or other authentication keys.

Credentials can be used to perform [Lateral Movement](../../12%20AML.TA0015%20-%20Lateral%20Movement/README.md) to access other AI services such as AI agents, LLMs, or AI inference APIs. Credentials could also give an adversary access to other software tools and data sources that are part of the AI DevOps lifecycle.

**Tactics**  [AML.TA0013 - Credential Access](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Demonstrated

**ATT&CK mapping**  [Local ATT&CK T1003](../../../../Enterprise/Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/README.md) · [MITRE ATT&CK T1003](https://attack.mitre.org/techniques/T1003/)

## Case studies

- [AML.CS0036 - AIKatz: Attacking LLM Desktop Applications](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s02)

## Mitigations

- [AML.M0011 - Restrict Library Loading](../../../Mitigations/AML.M0011%20-%20Restrict%20Library%20Loading.md) — Restrict library loading to block credential-dumping paths that inject or load malicious code into processes holding authentication material.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0090)
