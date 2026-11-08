# T1603 - Scheduled Task/Job

[Mobile](../../../README.md) / [Execution](../README.md)

Adversaries may abuse task scheduling functionality to facilitate initial or recurring execution of malicious code. On Android and iOS, APIs and libraries exist to facilitate scheduling tasks to execute at a specified date, time, or interval.

On Android, the `WorkManager` API allows asynchronous tasks to be scheduled with the system. `WorkManager` was introduced to unify task scheduling on Android, using `JobScheduler`, `GcmNetworkManager`, and `AlarmManager` internally. `WorkManager` offers a lot of flexibility for scheduling, including periodically, one time, or constraint-based (e.g. only when the device is charging).(Citation: Android WorkManager)

On iOS, the `NSBackgroundActivityScheduler` API allows asynchronous tasks to be scheduled with the system. The tasks can be scheduled to be repeating or non-repeating, however, the system chooses when the tasks will be executed. The app can choose the interval for repeating tasks, or the delay between scheduling and execution for one-time tasks.(Citation: Apple NSBackgroundActivityScheduler)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1603)

**Tactics**  [Execution](../README.md), [Persistence](../../03%20TA0028%20-%20Persistence/README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S1083 - Chameleon](../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has used the AlarmManager API to schedule tasks.(Citation: ThreatFabric_Chameleon_Dec2023) [ThreatFabric_Chameleon_Dec2023](https://www.threatfabric.com/blogs/android-banking-trojan-chameleon-is-back-in-action)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has utilized a timer to initiate a WebSocket connection.(Citation: ZimperiumOrtegaPratapagiri_GodFather_Jun2025) [ZimperiumOrtegaPratapagiri_GodFather_Jun2025](https://zimperium.com/blog/your-mobile-app-their-playground-the-dark-side-of-the-virtualization)
- [S0536 - GPlayed](../../../Threat%20Intelligence/Software/Malware/S0536%20-%20GPlayed.md) — [GPlayed](https://attack.mitre.org/software/S0536) has used timers to enable Wi-Fi, ping the C2 server, register the device with the C2, and register wake locks on the system.(Citation: Talos GPlayed) [Talos GPlayed](https://blog.talosintelligence.com/2018/10/gplayedtrojan.html)
- [S0545 - TERRACOTTA](../../../Threat%20Intelligence/Software/Malware/S0545%20-%20TERRACOTTA.md) — [TERRACOTTA](https://attack.mitre.org/software/S0545) has used timer events in React Native to initiate the foreground service.(Citation: WhiteOps TERRACOTTA) [WhiteOps TERRACOTTA](https://www.whiteops.com/blog/terracotta-android-malware-a-technical-study)
- [S0558 - Tiktok Pro](../../../Threat%20Intelligence/Software/Malware/S0558%20-%20Tiktok%20Pro.md) — [Tiktok Pro](https://attack.mitre.org/software/S0558) has contained an alarm that triggers every three minutes and timers for communicating with the C2.(Citation: Zscaler TikTok Spyware) [Zscaler TikTok Spyware](https://www.zscaler.com/blogs/security-research/tiktok-spyware)

## Detection strategies

- [DET0707 - Detection of Scheduled Task/Job](../../../Defenses/Detection%20Strategies/DET0707%20-%20Detection%20of%20Scheduled%20Task%20-%20Job.md)

## Sources

- [Apple NSBackgroundActivityScheduler](https://developer.apple.com/documentation/foundation/nsbackgroundactivityscheduler)
- [Android WorkManager](https://developer.android.com/topic/libraries/architecture/workmanager)
