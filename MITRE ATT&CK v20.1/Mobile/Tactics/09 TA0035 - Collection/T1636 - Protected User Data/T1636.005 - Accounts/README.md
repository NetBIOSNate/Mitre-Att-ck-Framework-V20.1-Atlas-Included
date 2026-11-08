# T1636.005 - Accounts

[Mobile](../../../../README.md) / [Collection](../../README.md) / [T1636 - Protected User Data](../README.md)

Adversaries may utilize standard operating system APIs to gather account data. On Android, this can be accomplished by using the AccountManager API. For example, adversaries may use the `getAccounts()` method to list all accounts.(Citation: Android_AccountManager_Feb2025) On iOS, this can be accomplished by using the Keychain services.  

If the device has been jailbroken or rooted, adversaries may be able to access [Accounts](https://attack.mitre.org/techniques/T1636/005) without the users’ knowledge or approval.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1636/005)

**Tactics**  [Collection](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S1243 - DCHSpy](../../../../Threat%20Intelligence/Software/Malware/S1243%20-%20DCHSpy.md) — [DCHSpy](https://attack.mitre.org/software/S1243) has collected account names and their types from the device.(Citation: Lookout_DCHSpy_July2025) [Lookout_DCHSpy_July2025](https://www.lookout.com/threat-intelligence/article/lookout-discovers-iranian-dchsy-surveillanceware)
- [S9005 - DocSwap](../../../../Threat%20Intelligence/Software/Malware/S9005%20-%20DocSwap.md) — [DocSwap](https://attack.mitre.org/software/S9005) has the ability to send registered account information.(Citation: EnkiWhiteHat_KimsukyDOCSWAP_Dec2025)(Citation: S2W_DocSwap_Mar2025) [EnkiWhiteHat_KimsukyDOCSWAP_Dec2025](https://www.enki.co.kr/en/media-center/blog/kimsuky-distributing-malicious-mobile-app-via-qr-code) · [S2W_DocSwap_Mar2025](https://medium.com/s2wblog/detailed-analysis-of-docswap-malware-disguised-as-security-document-viewer-218a728c36ff)
- [S1241 - RatMilad](../../../../Threat%20Intelligence/Software/Malware/S1241%20-%20RatMilad.md) — [RatMilad](https://attack.mitre.org/software/S1241) has collected account names and their types from the compromised device.(Citation: ZimperiumGupta_RatMilad_Oct2022) [ZimperiumGupta_RatMilad_Oct2022](https://zimperium.com/blog/we-smell-a-ratmilad-mobile-spyware)
- [S9006 - VajraSpy](../../../../Threat%20Intelligence/Software/Malware/S9006%20-%20VajraSpy.md) — [VajraSpy](https://attack.mitre.org/software/S9006) has requested for `android.permission.GET_ACCOUNTS`.(Citation: K7Dhanalakshmi_VajraSpy_April2022) [K7Dhanalakshmi_VajraSpy_April2022](https://labs.k7computing.com/index.php/vajraspy-an-android-rat/)

## Detection strategies

- [DET0635 - Detection of Accounts](../../../../Defenses/Detection%20Strategies/DET0635%20-%20Detection%20of%20Accounts.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — OS feature updates often enhance security and privacy around permissions.
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Access to accounts is an uncommonly needed permission, so users should be instructed to use extra scrutiny when granting access to their accounts.

## Sources

- [Android_AccountManager_Feb2025](https://developer.android.com/reference/android/accounts/AccountManager)
