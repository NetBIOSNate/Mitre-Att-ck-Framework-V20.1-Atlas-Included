# T1617 - Hooking

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may utilize hooking to hide the presence of artifacts associated with their behaviors to evade detection. Hooking can be used to modify return values or data structures of system APIs and function calls. This process typically involves using 3rd party root frameworks, such as Xposed or Magisk, with either a system exploit or pre-existing root access. By including custom modules for root frameworks, adversaries can hook system APIs and alter the return value and/or system data structures to alter functionality/visibility of various aspects of the system.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1617)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Mitigations

- [M1002 - Attestation](../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation can often detect rooted devices.
- [M1010 - Deploy Compromised Device Detection Method](../../../Defenses/Mitigations/M1010%20-%20Deploy%20Compromised%20Device%20Detection%20Method.md) — Mobile security products can often detect rooted devices.

## Procedure examples

- [S1208 - FjordPhantom](../../../Threat%20Intelligence/Software/Malware/S1208%20-%20FjordPhantom.md) — [FjordPhantom](https://attack.mitre.org/software/S1208) has used the hooking framework in a variety of ways, including returning false information to detection mechanisms, pretending that GooglePlayServices are unavailable, and manipulating UI functionality.(Citation: Promon FjordPhantom Oct2024) [Promon FjordPhantom Oct2024](https://promon.io/security-news/fjordphantom-android-malware)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has used the Xposed hooking framework to intercept HTTP requests and responses, capturing and exfiltrating sensitive information, such as credentials.(Citation: ZimperiumOrtegaPratapagiri_GodFather_Jun2025) [ZimperiumOrtegaPratapagiri_GodFather_Jun2025](https://zimperium.com/blog/your-mobile-app-their-playground-the-dark-side-of-the-virtualization)
- [S0407 - Monokle](../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can hook itself to appear invisible to the Process Manager.(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)

## Detection strategies

- [DET0719 - Detection of Hooking](../../../Defenses/Detection%20Strategies/DET0719%20-%20Detection%20of%20Hooking.md)
