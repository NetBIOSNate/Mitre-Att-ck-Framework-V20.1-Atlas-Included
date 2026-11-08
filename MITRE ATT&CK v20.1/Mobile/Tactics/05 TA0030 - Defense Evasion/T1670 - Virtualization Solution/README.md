# T1670 - Virtualization Solution

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may carry out malicious operations using virtualization solutions to escape from Android sandboxes and to avoid detection. Android uses sandboxes to separate resources and code execution between applications and the operating system.(Citation: Android Application Sandbox) There are a few virtualization solutions available on Android, such as the Android Virtualization Framework (AVF).(Citation: Android AVF Overview)  

 

Through virtualization solutions, adversaries may execute malicious operations without user knowledge. For example, adversaries may mimic a legitimate banking application’s functionalities in a virtual environment, thanks to the virtualization solution, while malicious code captures credentials.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1670)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S1208 - FjordPhantom](../../../Threat%20Intelligence/Software/Malware/S1208%20-%20FjordPhantom.md) — [FjordPhantom](https://attack.mitre.org/software/S1208) uses a virtualization solution to steal credentials.(Citation: Promon FjordPhantom Oct2024) [Promon FjordPhantom Oct2024](https://promon.io/security-news/fjordphantom-android-malware)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has used virtualization to create a separate virtual environment that mimicked legitimate banking and cryptocurrency applications.(Citation: ZimperiumOrtegaPratapagiri_GodFather_Jun2025) [ZimperiumOrtegaPratapagiri_GodFather_Jun2025](https://zimperium.com/blog/your-mobile-app-their-playground-the-dark-side-of-the-virtualization)

## Detection strategies

- [DET0606 - Detection of Virtualization Solution](../../../Defenses/Detection%20Strategies/DET0606%20-%20Detection%20of%20Virtualization%20Solution.md)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be encouraged to only install apps from authorized app stores, which are less likely to contain malicious applications.

## Sources

- [Android AVF Overview](https://source.android.com/docs/core/virtualization)
- [Android Application Sandbox](https://source.android.com/docs/security/app-sandbox)
