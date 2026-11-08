# T1641 - Data Manipulation

[Mobile](../../../README.md) / [Impact](../README.md)

Adversaries may insert, delete, or alter data in order to manipulate external outcomes or hide activity. By manipulating data, adversaries may attempt to affect a business process, organizational understanding, or decision making.

The type of modification and the impact it will have depends on the target application, process, and the goals and objectives of the adversary. For complex systems, an adversary would likely need special expertise and possibly access to specialized software related to the system, typically gained through a prolonged information gathering campaign, in order to have the desired impact.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1641)

**Tactics**  [Impact](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Sub-techniques

- [T1641.001 - Transmitted Data Manipulation](T1641.001%20-%20Transmitted%20Data%20Manipulation/README.md)

## Detection strategies

- [DET0660 - Detection of Data Manipulation](../../../Defenses/Detection%20Strategies/DET0660%20-%20Detection%20of%20Data%20Manipulation.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Recent OS versions have limited access to certain APIs unless certain conditions are met, making [Data Manipulation](https://attack.mitre.org/techniques/T1641) more difficult
