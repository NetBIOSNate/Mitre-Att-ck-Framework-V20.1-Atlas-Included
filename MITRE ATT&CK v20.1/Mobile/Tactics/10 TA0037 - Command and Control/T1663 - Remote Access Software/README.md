# T1663 - Remote Access Software

[Mobile](../../../README.md) / [Command and Control](../README.md)

Adversaries may use legitimate remote access software, such as `VNC`, `TeamViewer`, `AirDroid`, `AirMirror`, etc., to establish an interactive command and control channel to target mobile devices.  

Remote access applications may be installed and used post-compromise as an alternate communication channel for redundant access or as a way to establish an interactive remote session with the target device. They may also be used as a component of malware to establish a reverse connection to an adversary-controlled system or service. Installation of remote access tools may also include persistence.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1663)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S1094 - BRATA](../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can view a device through VNC.(Citation: cleafy_brata_0122) [cleafy_brata_0122](https://www.cleafy.com/cleafy-labs/how-brata-is-monitoring-your-bank-account)
- [S1092 - Escobar](../../../Threat%20Intelligence/Software/Malware/S1092%20-%20Escobar.md) — [Escobar](https://attack.mitre.org/software/S1092) can use VNC to remotely control an infected device.(Citation: Bleeipng Computer Escobar) [Bleeipng Computer Escobar](https://www.bleepingcomputer.com/news/security/android-malware-escobar-steals-your-google-authenticator-mfa-codes/)

## Detection strategies

- [DET0624 - Detection of Remote Access Software](../../../Defenses/Detection%20Strategies/DET0624%20-%20Detection%20of%20Remote%20Access%20Software.md)

## Mitigations

- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — When devices are enrolled in an EMM/MDM using device owner (iOS) or fully managed (Android) mode, the EMM/MDM can collect a list of installed applications on the device. An administrator can then act on, for example blocking, specific remote access applications from being installed on managed devices.
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be encouraged to be very careful with granting dangerous permissions, such as device administrator or access to device accessibility.
