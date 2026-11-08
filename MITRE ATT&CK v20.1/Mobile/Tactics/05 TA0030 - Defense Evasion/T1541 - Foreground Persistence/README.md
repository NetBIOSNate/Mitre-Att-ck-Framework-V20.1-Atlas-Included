# T1541 - Foreground Persistence

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may abuse Android's `startForeground()` API method to maintain continuous sensor access. Beginning in Android 9, idle applications running in the background no longer have access to device sensors, such as the camera, microphone, and gyroscope.(Citation: Android-SensorsOverview) Applications can retain sensor access by running in the foreground, using Android’s `startForeground()` API method. This informs the system that the user is actively interacting with the application, and it should not be killed. The only requirement to start a foreground service is showing a persistent notification to the user.(Citation: Android-ForegroundServices)

Malicious applications may abuse the `startForeground()` API method to continue running in the foreground, while presenting a notification to the user pretending to be a genuine application. This would allow unhindered access to the device’s sensors, assuming permission has been previously granted.(Citation: BlackHat Sutter Android Foreground 2019)

Malicious applications may also abuse the `startForeground()` API to inform the Android system that the user is actively interacting with the application, thus preventing it from being killed by the low memory killer.(Citation: TrendMicro-Yellow Camera)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1541)

**Tactics**  [Persistence](../../03%20TA0028%20-%20Persistence/README.md), [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — If a user sees a persistent notification they do not recognize, they should uninstall the source application and look for other unwanted applications or anomalies.

## Procedure examples

- [S1225 - CherryBlos](../../../Threat%20Intelligence/Software/Malware/S1225%20-%20CherryBlos.md) — [CherryBlos](https://attack.mitre.org/software/S1225) has utilized foreground services by showing a notification to evade detection.(Citation: TrendMicro_CherryBlos_July2023) [TrendMicro_CherryBlos_July2023](https://www.trendmicro.com/en_us/research/23/g/cherryblos-and-faketrade-android-malware-involved-in-scam-campai.html)
- [S9005 - DocSwap](../../../Threat%20Intelligence/Software/Malware/S9005%20-%20DocSwap.md) — [DocSwap](https://attack.mitre.org/software/S9005) has checked for the `FOREGROUND_SERVICE` permission.(Citation: EnkiWhiteHat_KimsukyDOCSWAP_Dec2025) [DocSwap](https://attack.mitre.org/software/S9005) has also used the StartForeground API to generate a notification saying “Tap to view more details or stop the app” in Korean and to maintain persistence.(Citation: S2W_DocSwap_Mar2025) [EnkiWhiteHat_KimsukyDOCSWAP_Dec2025](https://www.enki.co.kr/en/media-center/blog/kimsuky-distributing-malicious-mobile-app-via-qr-code) · [S2W_DocSwap_Mar2025](https://medium.com/s2wblog/detailed-analysis-of-docswap-malware-disguised-as-security-document-viewer-218a728c36ff)
- [S1054 - Drinik](../../../Threat%20Intelligence/Software/Malware/S1054%20-%20Drinik.md) — [Drinik](https://attack.mitre.org/software/S1054) has C2 commands that can move the malware in and out of the foreground. (Citation: cyble_drinik_1022) [cyble_drinik_1022](https://web.archive.org/web/20221114031945/https://blog.cyble.com/2022/10/27/drinik-malware-returns-with-advanced-capabilities-targeting-indian-taxpayers/)
- [S0485 - Mandrake](../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) uses foreground persistence to keep a service running. It shows the user a transparent notification to evade detection.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0545 - TERRACOTTA](../../../Threat%20Intelligence/Software/Malware/S0545%20-%20TERRACOTTA.md) — [TERRACOTTA](https://attack.mitre.org/software/S0545) has utilized foreground services.(Citation: WhiteOps TERRACOTTA) [WhiteOps TERRACOTTA](https://www.whiteops.com/blog/terracotta-android-malware-a-technical-study)
- [S0558 - Tiktok Pro](../../../Threat%20Intelligence/Software/Malware/S0558%20-%20Tiktok%20Pro.md) — [Tiktok Pro](https://attack.mitre.org/software/S0558) has shown a persistent notification to maintain access to device sensors.(Citation: Zscaler TikTok Spyware) [Zscaler TikTok Spyware](https://www.zscaler.com/blogs/security-research/tiktok-spyware)

## Detection strategies

- [DET0637 - Detection of Foreground Persistence](../../../Defenses/Detection%20Strategies/DET0637%20-%20Detection%20of%20Foreground%20Persistence.md)

## Sources

- [Android-SensorsOverview](https://developer.android.com/guide/topics/sensors/sensors_overview#sensors-practices)
- [Android-ForegroundServices](https://developer.android.com/guide/components/services.html#Foreground)
- [TrendMicro-Yellow Camera](https://blog.trendmicro.com/trendlabs-security-intelligence/fake-photo-beautification-apps-on-google-play-can-read-sms-verification-code-to-trigger-wireless-application-protocol-wap-carrier-billing/)
- [BlackHat Sutter Android Foreground 2019](https://i.blackhat.com/eu-19/Thursday/eu-19-Sutter-Simple-Spyware-Androids-Invisible-Foreground-Services-And-How-To-Abuse-Them.pdf)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-19.html)
