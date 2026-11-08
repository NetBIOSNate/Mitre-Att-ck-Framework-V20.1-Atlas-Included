# T1640 - Account Access Removal

[Mobile](../../../README.md) / [Impact](../README.md)

Adversaries may interrupt availability of system and network resources by inhibiting access to accounts utilized by legitimate users. Accounts may be deleted, locked, or manipulated (ex: credentials changed) to remove access to accounts.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1640)

**Tactics**  [Impact](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S0407 - Monokle](../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can reset the user's password/PIN.(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be taught that Device Administrator permissions are very dangerous, and very few applications need it.

## Detection strategies

- [DET0605 - Detection of Account Access Removal](../../../Defenses/Detection%20Strategies/DET0605%20-%20Detection%20of%20Account%20Access%20Removal.md)
