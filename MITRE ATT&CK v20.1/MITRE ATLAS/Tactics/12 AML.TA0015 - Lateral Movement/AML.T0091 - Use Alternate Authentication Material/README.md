# AML.T0091 - Use Alternate Authentication Material

[MITRE ATLAS](../../../README.md) / [AML.TA0015 - Lateral Movement](../README.md)

Adversaries may use alternate authentication material, such as password hashes, Kerberos tickets, and application access tokens, in order to move laterally within an environment and bypass normal system access controls.

AI services commonly use alternate authentication material as a primary means for users to make queries, making them vulnerable to this technique.

**Tactics**  [AML.TA0015 - Lateral Movement](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1550](../../../../Enterprise/Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/README.md) · [MITRE ATT&CK T1550](https://attack.mitre.org/techniques/T1550/)

## Sub-techniques

- [AML.T0091.000 - Application Access Token](AML.T0091.000%20-%20Application%20Access%20Token/README.md)
- [AML.T0091.001 - Web Session Cookie](AML.T0091.001%20-%20Web%20Session%20Cookie/README.md)

## Mitigations

- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Enforce authorization and monitor production AI API use for anomalous activity associated with replayed access tokens.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0091)
