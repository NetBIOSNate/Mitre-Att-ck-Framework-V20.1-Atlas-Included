# T1628.003 - Conceal Multimedia Files

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1628 - Hide Artifacts](../README.md)

Adversaries may attempt to hide multimedia files from the user. By doing so, adversaries may conceal captured files, such as pictures, videos and/or screenshots, then later exfiltrate those files.  

Specific to Android devices, if the `.nomedia` file is present in a folder, multimedia files in that folder will not be visible to the user in the Gallery application. Additionally, other applications are asked not to scan the folder with the `.nomedia` file, effectively making the folder appear invisible to the user.  

This technique is often used by stalkerware and spyware applications.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1628/003)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Procedure examples

- [G0112 - Windshift](../../../../Threat%20Intelligence/Groups/G0112%20-%20Windshift.md) — [Windshift](https://attack.mitre.org/groups/G0112) has hidden multimedia files from the user.(Citation: Cyfirma Bahamut) [Cyfirma Bahamut](https://www.cyfirma.com/outofband/apt-bahamut-attacks-indian-intelligence-operative-using-android-malware/)

## Detection strategies

- [DET0659 - Detection of Conceal Multimedia Files](../../../../Defenses/Detection%20Strategies/DET0659%20-%20Detection%20of%20Conceal%20Multimedia%20Files.md)

## Mitigations

- [M1059 - Do Not Mitigate](../../../../Defenses/Mitigations/M1059%20-%20Do%20Not%20Mitigate.md) — [Conceal Multimedia Files](https://attack.mitre.org/techniques/T1628/003) likely should not be mitigated with preventative controls because the `.nomedia` file may be used legitimately.
