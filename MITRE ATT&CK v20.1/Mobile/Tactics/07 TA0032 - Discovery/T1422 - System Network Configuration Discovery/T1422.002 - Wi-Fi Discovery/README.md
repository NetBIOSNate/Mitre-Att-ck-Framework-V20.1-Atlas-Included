# T1422.002 - Wi-Fi Discovery

[Mobile](../../../../README.md) / [Discovery](../../README.md) / [T1422 - System Network Configuration Discovery](../README.md)

Adversaries may search for information about Wi-Fi networks, such as network names and passwords, on compromised systems. Adversaries may use Wi-Fi information as part of [Discovery](https://attack.mitre.org/tactics/TA0032) or [Credential Access](https://attack.mitre.org/tactics/TA0031) activity to support both ongoing and future campaigns.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1422/002)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S1079 - BOULDSPY](../../../../Threat%20Intelligence/Software/Malware/S1079%20-%20BOULDSPY.md) — [BOULDSPY](https://attack.mitre.org/software/S1079) can collect network information, such as IP address, SIM card information, and Wi-Fi information.(Citation: lookout_bouldspy_0423) [lookout_bouldspy_0423](https://www.lookout.com/blog/iranian-spyware-bouldspy)
- [S0425 - Corona Updates](../../../../Threat%20Intelligence/Software/Malware/S0425%20-%20Corona%20Updates.md) — [Corona Updates](https://attack.mitre.org/software/S0425) can collect device network configuration information, such as Wi-Fi SSID and IMSI.(Citation: TrendMicro Coronavirus Updates) [TrendMicro Coronavirus Updates](https://blog.trendmicro.com/trendlabs-security-intelligence/coronavirus-update-app-leads-to-project-spy-android-and-ios-spyware/)
- [S9005 - DocSwap](../../../../Threat%20Intelligence/Software/Malware/S9005%20-%20DocSwap.md) — [DocSwap](https://attack.mitre.org/software/S9005) has checked for the `ACCESS_WIFI_STATE` and `CHANGE_WIFI_STATE` permissions.(Citation: EnkiWhiteHat_KimsukyDOCSWAP_Dec2025) [EnkiWhiteHat_KimsukyDOCSWAP_Dec2025](https://www.enki.co.kr/en/media-center/blog/kimsuky-distributing-malicious-mobile-app-via-qr-code)
- [S1077 - Hornbill](../../../../Threat%20Intelligence/Software/Malware/S1077%20-%20Hornbill.md) — [Hornbill](https://attack.mitre.org/software/S1077) can collect a device's phone number and IMEI, and can check to see if Wi-Fi is enabled.(Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)
- [S0463 - INSOMNIA](../../../../Threat%20Intelligence/Software/Malware/S0463%20-%20INSOMNIA.md) — [INSOMNIA](https://attack.mitre.org/software/S0463) can collect the device’s phone number, ICCID, IMEI, and the currently active network interface (Wi-Fi or cellular).(Citation: Google Project Zero Insomnia) [Google Project Zero Insomnia](https://googleprojectzero.blogspot.com/2019/08/implant-teardown.html)
- [S9048 - KoSpy](../../../../Threat%20Intelligence/Software/Malware/S9048%20-%20KoSpy.md) — [KoSpy](https://attack.mitre.org/software/S9048) has collected Wi-Fi network details using dynamically loaded plugins.(Citation: Lookout_KoSpy_March2025) [Lookout_KoSpy_March2025](https://security.lookout.com/threat-intelligence/article/lookout-discovers-new-spyware-by-north-korean-apt37)
- [S1185 - LightSpy](../../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) uses the WifiList (or `libWifiList`) plugin to gather Wi-Fi network information, such as the SSID, BSSID, signal strength (RSSI), channel, security type, and previously saved networks.(Citation: MelikovBlackBerry LightSpy 2024)(Citation: LinkedIn Dmitry LightSpy 2025)(Citation: Threatfabric LightSpy 2024)(Citation: Threatfabric LightSpy 2023) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [MelikovBlackBerry LightSpy 2024](https://blogs.blackberry.com/en/2024/04/lightspy-returns-renewed-espionage-campaign-targets-southern-asia-possibly-india) · [Threatfabric LightSpy 2023](https://www.threatfabric.com/blogs/lightspy-mapt-mobile-payment-system-attack) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [S0407 - Monokle](../../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) checks if the device is connected via Wi-Fi or mobile data.(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)
- [S0316 - Pegasus for Android](../../../../Threat%20Intelligence/Software/Malware/S0316%20-%20Pegasus%20for%20Android.md) — [Pegasus for Android](https://attack.mitre.org/software/S0316) checks if the device is on Wi-Fi, a cellular network, and is roaming.(Citation: Lookout-PegasusAndroid) [Lookout-PegasusAndroid](https://blog.lookout.com/blog/2017/04/03/pegasus-android/)
- [S0326 - RedDrop](../../../../Threat%20Intelligence/Software/Malware/S0326%20-%20RedDrop.md) — [RedDrop](https://attack.mitre.org/software/S0326) collects and exfiltrates information including IMEI, IMSI, MNC, MCC, nearby Wi-Fi networks, and other device and SIM-related info.(Citation: Wandera-RedDrop) [Wandera-RedDrop](https://web.archive.org/web/20180618225805/https://www.wandera.com/reddrop-malware/)
- [S1056 - TianySpy](../../../../Threat%20Intelligence/Software/Malware/S1056%20-%20TianySpy.md) — [TianySpy](https://attack.mitre.org/software/S1056) can check to see if Wi-Fi is enabled.(Citation: trendmicro_tianyspy_0122) [trendmicro_tianyspy_0122](https://www.trendmicro.com/en_us/research/22/a/tianyspy-malware-uses-smishing-disguised-as-message-from-telco.html)
- [S0427 - TrickMo](../../../../Threat%20Intelligence/Software/Malware/S0427%20-%20TrickMo.md) — [TrickMo](https://attack.mitre.org/software/S0427) can collect device network configuration information such as IMSI, IMEI, and Wi-Fi connection state.(Citation: SecurityIntelligence TrickMo) [SecurityIntelligence TrickMo](https://securityintelligence.com/posts/trickbot-pushing-a-2fa-bypass-app-to-bank-customers-in-germany/)
- [S9006 - VajraSpy](../../../../Threat%20Intelligence/Software/Malware/S9006%20-%20VajraSpy.md) — [VajraSpy](https://attack.mitre.org/software/S9006) has scanned for Wi-Fi networks.(Citation: ESET_VajraSpy_Feb2024) [ESET_VajraSpy_Feb2024](https://www.welivesecurity.com/en/eset-research/vajraspy-patchwork-espionage-apps/)

## Detection strategies

- [DET0709 - Detection of Wi-Fi Discovery](../../../../Defenses/Detection%20Strategies/DET0709%20-%20Detection%20of%20Wi-Fi%20Discovery.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 10 introduced changes that prevent normal applications from accessing sensitive device identifiers.(Citation: TelephonyManager) [TelephonyManager](https://developer.android.com/reference/android/telephony/TelephonyManager.html)
