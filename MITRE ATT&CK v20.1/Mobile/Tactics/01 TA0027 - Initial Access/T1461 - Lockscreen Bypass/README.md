# T1461 - Lockscreen Bypass

[Mobile](../../../README.md) / [Initial Access](../README.md)

An adversary with physical access to a mobile device may seek to bypass the device’s lockscreen. Several methods exist to accomplish this, including:

* Biometric spoofing: If biometric authentication is used, an adversary could attempt to spoof a mobile device’s biometric authentication mechanism. Both iOS and Android partly mitigate this attack by requiring the device’s passcode rather than biometrics to unlock the device after every device restart, and after a set or random amount of time.(Citation: SRLabs-Fingerprint)(Citation: TheSun-FaceID)
* Unlock code bypass: An adversary could attempt to brute-force or otherwise guess the lockscreen passcode (typically a PIN or password), including physically observing (“shoulder surfing”) the device owner’s use of the lockscreen passcode. Mobile OS vendors partly mitigate this by implementing incremental backoff timers after a set number of failed unlock attempts, as well as a configurable full device wipe after several failed unlock attempts.
* Vulnerability exploit: Techniques have been periodically demonstrated that exploit mobile devices to bypass the lockscreen. The vulnerabilities are generally patched by the device or OS vendor once disclosed.(Citation: Wired-AndroidBypass)(Citation: Kaspersky-iOSBypass)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1461)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S1094 - BRATA](../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can request the user unlock the device, or remotely unlock the device.(Citation: securelist_brata_0819) [securelist_brata_0819](https://securelist.com/spying-android-rat-from-brazil-brata/92775/)
- [S1083 - Chameleon](../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has the ability to bypass the biometric prompt for unlocking an infected device, forcing the victim to use PIN authentication. To do so, [Chameleon](https://attack.mitre.org/software/S1083) will first check specified conditions, then will use the AccessibilityEvent action to transition from biometric authentication to PIN authentication.(Citation: ThreatFabric_Chameleon_Dec2023) [ThreatFabric_Chameleon_Dec2023](https://www.threatfabric.com/blogs/android-banking-trojan-chameleon-is-back-in-action)
- [S1092 - Escobar](../../../Threat%20Intelligence/Software/Malware/S1092%20-%20Escobar.md) — [Escobar](https://attack.mitre.org/software/S1092) can request the `DISABLE_KEYGUARD` permission to disable the device lock screen password.(Citation: Bleeipng Computer Escobar) [Bleeipng Computer Escobar](https://www.bleepingcomputer.com/news/security/android-malware-escobar-steals-your-google-authenticator-mfa-codes/)
- [S9006 - VajraSpy](../../../Threat%20Intelligence/Software/Malware/S9006%20-%20VajraSpy.md) — [VajraSpy](https://attack.mitre.org/software/S9006) has requested for `android.permission.DISABLE_KEYGUARD` to disable the device lock screen password.(Citation: K7Dhanalakshmi_VajraSpy_April2022) [K7Dhanalakshmi_VajraSpy_April2022](https://labs.k7computing.com/index.php/vajraspy-an-android-rat/)

## Mitigations

- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — Enterprises can provision policies to mobile devices that require a minimum complexity (length, character requirements, etc.) for the device passcode, and cause the device to wipe all data if an incorrect passcode is entered too many times. Both policies would mitigate brute-force, guessing, or shoulder surfing of the device passcode. Enterprises can also provision policies to disable biometric authentication, however, biometric authentication can help make using a longer, more complex passcode more practical because it does not need to be entered as frequently.
- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — OS security updates typically contain exploit patches when disclosed.

## Detection strategies

- [DET0645 - Detection of Lockscreen Bypass](../../../Defenses/Detection%20Strategies/DET0645%20-%20Detection%20of%20Lockscreen%20Bypass.md)

## Sources

- [Wired-AndroidBypass](https://www.wired.com/2015/09/hack-brief-new-emergency-number-hack-easily-bypasses-android-lock-screens/)
- [Kaspersky-iOSBypass](https://threatpost.com/ios-10-passcode-bypass-can-access-photos-contacts/122033/)
- [TheSun-FaceID](https://www.thesun.co.uk/tech/5584082/iphone-x-face-unlock-tricked-broken/)
- [SRLabs-Fingerprint](https://srlabs.de/bites/spoofing-fingerprints/)
