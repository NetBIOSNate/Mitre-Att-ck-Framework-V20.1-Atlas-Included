# T1628 - Hide Artifacts

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may attempt to hide artifacts associated with their behaviors to evade detection. Mobile operating systems have features and developer APIs to hide various artifacts, such as an application’s launcher icon. These APIs have legitimate usages, such as hiding an icon to avoid application drawer clutter when an application does not have a usable interface. Adversaries may abuse these features and APIs to hide artifacts from the user to evade detection.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1628)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Sub-techniques

- [T1628.003 - Conceal Multimedia Files](T1628.003%20-%20Conceal%20Multimedia%20Files/README.md)
- [T1628.001 - Suppress Application Icon](T1628.001%20-%20Suppress%20Application%20Icon/README.md)
- [T1628.002 - User Evasion](T1628.002%20-%20User%20Evasion/README.md)

## Detection strategies

- [DET0640 - Detection of Hide Artifacts](../../../Defenses/Detection%20Strategies/DET0640%20-%20Detection%20of%20Hide%20Artifacts.md)
