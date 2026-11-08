# T1642 - Endpoint Denial of Service

[Mobile](../../../README.md) / [Impact](../README.md)

Adversaries may perform Endpoint Denial of Service (DoS) attacks to degrade or block the availability of services to users.

On Android versions prior to 7, apps can abuse Device Administrator access to reset the device lock passcode, preventing the user from unlocking the device. After Android 7, only device or profile owners (e.g. MDMs) can reset the device’s passcode.(Citation: Android resetPassword)

On iOS devices, this technique does not work because mobile device management servers can only remove the screen lock passcode; they cannot set a new passcode. However, on jailbroken devices, malware has been discovered that can lock the user out of the device.(Citation: Xiao-KeyRaider)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1642)

**Tactics**  [Impact](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S0323 - Charger](../../../Threat%20Intelligence/Software/Malware/S0323%20-%20Charger.md) — [Charger](https://attack.mitre.org/software/S0323) locks the device if it is granted admin permissions, displaying a message demanding a ransom payment.(Citation: CheckPoint-Charger) [CheckPoint-Charger](http://blog.checkpoint.com/2017/01/24/charger-malware/)
- [S0522 - Exobot](../../../Threat%20Intelligence/Software/Malware/S0522%20-%20Exobot.md) — [Exobot](https://attack.mitre.org/software/S0522) can lock the device with a password and permanently disable the screen.(Citation: Threat Fabric Exobot) [Threat Fabric Exobot](https://www.threatfabric.com/blogs/exobot_android_banking_trojan_on_the_rise.html)
- [S0536 - GPlayed](../../../Threat%20Intelligence/Software/Malware/S0536%20-%20GPlayed.md) — [GPlayed](https://attack.mitre.org/software/S0536) can lock the user out of the device by showing a persistent overlay.(Citation: Talos GPlayed) [Talos GPlayed](https://blog.talosintelligence.com/2018/10/gplayedtrojan.html)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has used the DeleteSpring plugin to render the device’s user interface inoperable by disabling SpringBoard, which is iOS's home screen manager.(Citation: LinkedIn Dmitry LightSpy 2025) [LightSpy](https://attack.mitre.org/software/S1185) has used the BootDestroy plugin to prevent the victim device from booting by modifying the NVRAM parameter `auto-boot` to `false`.(Citation: LinkedIn Dmitry LightSpy 2025) Additionally, [LightSpy](https://attack.mitre.org/software/S1185) has renamed the Wi-Fi daemon to disable wireless connectivity.(Citation: LinkedIn Dmitry LightSpy 2025) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/)
- [S0298 - Xbot](../../../Threat%20Intelligence/Software/Tools/S0298%20-%20Xbot.md) — [Xbot](https://attack.mitre.org/software/S0298) can remotely lock infected Android devices and ask for a ransom.(Citation: PaloAlto-Xbot) [PaloAlto-Xbot](http://researchcenter.paloaltonetworks.com/2016/02/new-android-trojan-xbot-phishes-credit-cards-and-bank-accounts-encrypts-devices-for-ransom/)

## Mitigations

- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 7 changed how the Device Administrator password APIs function.
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be cautioned against granting administrative access to applications.

## Detection strategies

- [DET0627 - Detection of Endpoint Denial of Service](../../../Defenses/Detection%20Strategies/DET0627%20-%20Detection%20of%20Endpoint%20Denial%20of%20Service.md)

## Sources

- [Xiao-KeyRaider](http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/)
- [Android resetPassword](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#resetPassword%28java.lang.String,%20int%29)
