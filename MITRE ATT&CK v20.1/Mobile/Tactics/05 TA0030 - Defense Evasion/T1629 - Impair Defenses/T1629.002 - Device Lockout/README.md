# T1629.002 - Device Lockout

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1629 - Impair Defenses](../README.md)

An adversary may seek to inhibit user interaction by locking the legitimate user out of the device. This is typically accomplished by requesting device administrator permissions and then locking the screen using `DevicePolicyManager.lockNow()`. Other novel techniques for locking the user out of the device have been observed, such as showing a persistent overlay, using carefully crafted “call” notification screens, and locking HTML pages in the foreground. These techniques can be very difficult to get around, and typically require booting the device into safe mode to uninstall the malware.(Citation: Microsoft MalLockerB)(Citation: Talos GPlayed)(Citation: securelist rotexy 2018)

Prior to Android 7, device administrators were able to reset the device lock passcode to prevent the user from unlocking the device. The release of Android 7 introduced updates that only allow device or profile owners (e.g. MDMs) to reset the device’s passcode.(Citation: Android resetPassword)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1629/002)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Procedure examples

- [S0524 - AndroidOS/MalLocker.B](../../../../Threat%20Intelligence/Software/Malware/S0524%20-%20AndroidOS%20-%20MalLocker.B.md) — [AndroidOS/MalLocker.B](https://attack.mitre.org/software/S0524) can prevent the user from interacting with the UI by using a carefully crafted "call" notification screen. This is coupled with overriding the `onUserLeaveHint()` callback method to spawn a new notification instance when the current one is dismissed. (Citation: Microsoft MalLockerB) [Microsoft MalLockerB](https://www.microsoft.com/security/blog/2020/10/08/sophisticated-new-android-malware-marks-the-latest-evolution-of-mobile-ransomware/)
- [S0411 - Rotexy](../../../../Threat%20Intelligence/Software/Malware/S0411%20-%20Rotexy.md) — [Rotexy](https://attack.mitre.org/software/S0411) can lock an HTML page in the foreground, requiring the user enter credit card information that matches information previously intercepted in SMS messages, such as the last 4 digits of a credit card number. If attempts to revoke administrator permissions are detected, [Rotexy](https://attack.mitre.org/software/S0411) periodically switches off the phone screen to inhibit permission removal.(Citation: securelist rotexy 2018) [securelist rotexy 2018](https://securelist.com/the-rotexy-mobile-trojan-banker-and-ransomware/88893/)
- [S0427 - TrickMo](../../../../Threat%20Intelligence/Software/Malware/S0427%20-%20TrickMo.md) — [TrickMo](https://attack.mitre.org/software/S0427) can prevent the user from interacting with the UI by showing a WebView with a persistent cursor.(Citation: SecurityIntelligence TrickMo) [SecurityIntelligence TrickMo](https://securityintelligence.com/posts/trickbot-pushing-a-2fa-bypass-app-to-bank-customers-in-germany/)

## Mitigations

- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Recent versions of Android modified how device administrator applications are uninstalled, making it easier for the user to remove them. Android 7 introduced updates that revoke standard device administrators’ ability to reset the device’s passcode.

## Detection strategies

- [DET0603 - Detection of Device Lockout](../../../../Defenses/Detection%20Strategies/DET0603%20-%20Detection%20of%20Device%20Lockout.md)

## Sources

- [Microsoft MalLockerB](https://www.microsoft.com/security/blog/2020/10/08/sophisticated-new-android-malware-marks-the-latest-evolution-of-mobile-ransomware/)
- [Android resetPassword](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#resetPassword%28java.lang.String,%20int%29)
- [securelist rotexy 2018](https://securelist.com/the-rotexy-mobile-trojan-banker-and-ransomware/88893/)
- [Talos GPlayed](https://blog.talosintelligence.com/2018/10/gplayedtrojan.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-22.html)
