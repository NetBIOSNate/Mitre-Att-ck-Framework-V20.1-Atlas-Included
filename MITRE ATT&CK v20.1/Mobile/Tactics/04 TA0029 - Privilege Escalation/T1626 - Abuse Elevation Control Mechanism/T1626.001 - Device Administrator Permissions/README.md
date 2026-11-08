# T1626.001 - Device Administrator Permissions

[Mobile](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1626 - Abuse Elevation Control Mechanism](../README.md)

Adversaries may abuse Android’s device administration API to obtain a higher degree of control over the device. By abusing the API, adversaries can perform several nefarious actions, such as resetting the device’s password for [Endpoint Denial of Service](https://attack.mitre.org/techniques/T1642), factory resetting the device for [File Deletion](https://attack.mitre.org/techniques/T1630/002) and to delete any traces of the malware, disabling all the device’s cameras, or to make it more difficult to uninstall the app.

Device administrators must be approved by the user at runtime, with a system popup showing which actions have been requested by the app. In conjunction with other techniques, such as [Input Injection](https://attack.mitre.org/techniques/T1516), an app can programmatically grant itself administrator permissions without any user input.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1626/001)

**Tactics**  [Privilege Escalation](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Detection strategies

- [DET0630 - Detection of Device Administrator Permissions](../../../../Defenses/Detection%20Strategies/DET0630%20-%20Detection%20of%20Device%20Administrator%20Permissions.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Changes were introduced in Android 7 to make abuse of device administrator permissions more difficult.(Citation: GoogleIO2016) [GoogleIO2016](https://www.youtube.com/watch?v=XZzLjllizYs)
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should scrutinize every device administration permission request. If the request is not expected or the user does not recognize the application, the application should be uninstalled immediately.

## Procedure examples

- [S1061 - AbstractEmu](../../../../Threat%20Intelligence/Software/Malware/S1061%20-%20AbstractEmu.md) — [AbstractEmu](https://attack.mitre.org/software/S1061) can modify system settings to give itself device administrator privileges.(Citation: lookout_abstractemu_1021) [lookout_abstractemu_1021](https://www.lookout.com/blog/lookout-discovers-global-rooting-malware-campaign)
- [S0540 - Asacub](../../../../Threat%20Intelligence/Software/Malware/S0540%20-%20Asacub.md) — [Asacub](https://attack.mitre.org/software/S0540) can request device administrator permissions.(Citation: Securelist Asacub) [Securelist Asacub](https://securelist.com/the-rise-of-mobile-banker-asacub/87591/)
- [S9004 - Crocodilus](../../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) has the ability to request device administrator permissions.(Citation: ThreatFabric_Crocodilus_March2025) [ThreatFabric_Crocodilus_March2025](https://www.threatfabric.com/blogs/exposing-crocodilus-new-device-takeover-malware-targeting-android-devices)
- [S0522 - Exobot](../../../../Threat%20Intelligence/Software/Malware/S0522%20-%20Exobot.md) — [Exobot](https://attack.mitre.org/software/S0522) can request device administrator permissions.(Citation: Threat Fabric Exobot) [Threat Fabric Exobot](https://www.threatfabric.com/blogs/exobot_android_banking_trojan_on_the_rise.html)
- [S0536 - GPlayed](../../../../Threat%20Intelligence/Software/Malware/S0536%20-%20GPlayed.md) — [GPlayed](https://attack.mitre.org/software/S0536) can request device administrator permissions.(Citation: Talos GPlayed) [Talos GPlayed](https://blog.talosintelligence.com/2018/10/gplayedtrojan.html)
- [S1077 - Hornbill](../../../../Threat%20Intelligence/Software/Malware/S1077%20-%20Hornbill.md) — [Hornbill](https://attack.mitre.org/software/S1077) can request device administrator privileges.(Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)
- [S0539 - Red Alert 2.0](../../../../Threat%20Intelligence/Software/Malware/S0539%20-%20Red%20Alert%202.0.md) — [Red Alert 2.0](https://attack.mitre.org/software/S0539) can request device administrator permissions.(Citation: Sophos Red Alert 2.0) [Sophos Red Alert 2.0](https://news.sophos.com/en-us/2018/07/23/red-alert-2-0-android-trojan-targets-security-seekers/)
- [S1082 - Sunbird](../../../../Threat%20Intelligence/Software/Malware/S1082%20-%20Sunbird.md) — [Sunbird](https://attack.mitre.org/software/S1082) can request device administrator privileges. (Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)
- [S0318 - XLoader for Android](../../../../Threat%20Intelligence/Software/Malware/S0318%20-%20XLoader%20for%20Android.md) — [XLoader for Android](https://attack.mitre.org/software/S0318) requests Android Device Administrator access.(Citation: TrendMicro-XLoader) [TrendMicro-XLoader](https://blog.trendmicro.com/trendlabs-security-intelligence/xloader-android-spyware-and-banking-trojan-distributed-via-dns-spoofing/)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-22.html)
