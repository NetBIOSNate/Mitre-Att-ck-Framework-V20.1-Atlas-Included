# T1626 - Abuse Elevation Control Mechanism

[Mobile](../../../README.md) / [Privilege Escalation](../README.md)

Adversaries may circumvent mechanisms designed to control elevated privileges to gain higher-level permissions. Most modern systems contain native elevation control mechanisms that are intended to limit privileges that a user can gain on a machine. Authorization has to be granted to specific users in order to perform tasks that are designated as higher risk. An adversary can use several methods to take advantage of built-in control mechanisms in order to escalate privileges on a system.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1626)

**Tactics**  [Privilege Escalation](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Sub-techniques

- [T1626.001 - Device Administrator Permissions](T1626.001%20-%20Device%20Administrator%20Permissions/README.md)

## Mitigations

- [M1013 - Application Developer Guidance](../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Applications very rarely require administrator permission. Developers should be cautioned against using this higher degree of access to avoid being flagged as a potentially malicious application.

## Detection strategies

- [DET0642 - Detection of Abuse Elevation Control Mechanism](../../../Defenses/Detection%20Strategies/DET0642%20-%20Detection%20of%20Abuse%20Elevation%20Control%20Mechanism.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-22.html)
