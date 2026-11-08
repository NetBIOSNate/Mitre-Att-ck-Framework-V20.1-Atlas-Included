# T1422.001 - Internet Connection Discovery

[Mobile](../../../../README.md) / [Discovery](../../README.md) / [T1422 - System Network Configuration Discovery](../README.md)

Adversaries may check for Internet connectivity on compromised systems. This may be performed during automated discovery and can be accomplished in numerous ways such as using `adb shell netstat` for Android.(Citation: adb_commands)

Adversaries may use the results and responses from these requests to determine if the mobile devices are capable of communicating with adversary-owned C2 servers before attempting to connect to them. The results may also be used to identify routes, redirectors, and proxy servers.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1422/001)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S1061 - AbstractEmu](../../../../Threat%20Intelligence/Software/Malware/S1061%20-%20AbstractEmu.md) — [AbstractEmu](https://attack.mitre.org/software/S1061) can collect device IP address and SIM information.(Citation: lookout_abstractemu_1021) [lookout_abstractemu_1021](https://www.lookout.com/blog/lookout-discovers-global-rooting-malware-campaign)
- [S0540 - Asacub](../../../../Threat%20Intelligence/Software/Malware/S0540%20-%20Asacub.md) — [Asacub](https://attack.mitre.org/software/S0540) can collect various pieces of device network configuration information, such as mobile network operator.(Citation: Securelist Asacub) [Securelist Asacub](https://securelist.com/the-rise-of-mobile-banker-asacub/87591/)
- [S1079 - BOULDSPY](../../../../Threat%20Intelligence/Software/Malware/S1079%20-%20BOULDSPY.md) — [BOULDSPY](https://attack.mitre.org/software/S1079) can collect network information, such as IP address, SIM card information, and Wi-Fi information.(Citation: lookout_bouldspy_0423) [lookout_bouldspy_0423](https://www.lookout.com/blog/iranian-spyware-bouldspy)
- [S0529 - CarbonSteal](../../../../Threat%20Intelligence/Software/Malware/S0529%20-%20CarbonSteal.md) — [CarbonSteal](https://attack.mitre.org/software/S0529) has gathered device metadata, including model, manufacturer, SD card size, disk usage, memory, CPU, and serial number.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S0425 - Corona Updates](../../../../Threat%20Intelligence/Software/Malware/S0425%20-%20Corona%20Updates.md) — [Corona Updates](https://attack.mitre.org/software/S0425) can collect device network configuration information, such as Wi-Fi SSID and IMSI.(Citation: TrendMicro Coronavirus Updates) [TrendMicro Coronavirus Updates](https://blog.trendmicro.com/trendlabs-security-intelligence/coronavirus-update-app-leads-to-project-spy-android-and-ios-spyware/)
- [S0478 - EventBot](../../../../Threat%20Intelligence/Software/Malware/S0478%20-%20EventBot.md) — [EventBot](https://attack.mitre.org/software/S0478) can gather device network information.(Citation: Cybereason EventBot) [Cybereason EventBot](https://www.cybereason.com/blog/eventbot-a-new-mobile-banking-trojan-is-born)
- [S0522 - Exobot](../../../../Threat%20Intelligence/Software/Malware/S0522%20-%20Exobot.md) — [Exobot](https://attack.mitre.org/software/S0522) can obtain the device’s IMEI, phone number, and IP address.(Citation: Threat Fabric Exobot) [Threat Fabric Exobot](https://www.threatfabric.com/blogs/exobot_android_banking_trojan_on_the_rise.html)
- [S0405 - Exodus](../../../../Threat%20Intelligence/Software/Malware/S0405%20-%20Exodus.md) — [Exodus](https://attack.mitre.org/software/S0405) One queries the device for its IMEI code and the phone number in order to validate the target of a new infection.(Citation: SWB Exodus March 2019) [SWB Exodus March 2019](https://web.archive.org/web/20200314194610/https://securitywithoutborders.org/blog/2019/03/29/exodus.html)
- [S0509 - FakeSpy](../../../../Threat%20Intelligence/Software/Malware/S0509%20-%20FakeSpy.md) — [FakeSpy](https://attack.mitre.org/software/S0509) can collect device networking information, including phone number, IMEI, and IMSI.(Citation: Cybereason FakeSpy) [Cybereason FakeSpy](https://www.cybereason.com/blog/fakespy-masquerades-as-postal-service-apps-around-the-world)
- [S1093 - FlyTrap](../../../../Threat%20Intelligence/Software/Malware/S1093%20-%20FlyTrap.md) — [FlyTrap](https://attack.mitre.org/software/S1093) can collect IP address and network configuration information.(Citation: Trend Micro FlyTrap) [Trend Micro FlyTrap](https://news.trendmicro.com/2021/08/17/flytrap-android-malware-is-taking-over-facebook-accounts-protect-yourself-with-a-malware-scanner/)
- [S1077 - Hornbill](../../../../Threat%20Intelligence/Software/Malware/S1077%20-%20Hornbill.md) — [Hornbill](https://attack.mitre.org/software/S1077) can collect a device's phone number and IMEI, and can check to see if WiFi is enabled.(Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)
- [S0463 - INSOMNIA](../../../../Threat%20Intelligence/Software/Malware/S0463%20-%20INSOMNIA.md) — [INSOMNIA](https://attack.mitre.org/software/S0463) can collect the device’s phone number, ICCID, IMEI, and the currently active network interface (Wi-Fi or cellular).(Citation: Google Project Zero Insomnia) [Google Project Zero Insomnia](https://googleprojectzero.blogspot.com/2019/08/implant-teardown.html)
- [S0407 - Monokle](../../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) checks if the device is connected via Wi-Fi or mobile data.(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)
- [S0316 - Pegasus for Android](../../../../Threat%20Intelligence/Software/Malware/S0316%20-%20Pegasus%20for%20Android.md) — [Pegasus for Android](https://attack.mitre.org/software/S0316) checks if the device is on Wi-Fi, a cellular network, and is roaming.(Citation: Lookout-PegasusAndroid) [Lookout-PegasusAndroid](https://blog.lookout.com/blog/2017/04/03/pegasus-android/)
- [S0326 - RedDrop](../../../../Threat%20Intelligence/Software/Malware/S0326%20-%20RedDrop.md) — [RedDrop](https://attack.mitre.org/software/S0326) collects and exfiltrates information including IMEI, IMSI, MNC, MCC, nearby Wi-Fi networks, and other device and SIM-related info.(Citation: Wandera-RedDrop) [Wandera-RedDrop](https://web.archive.org/web/20180618225805/https://www.wandera.com/reddrop-malware/)
- [S0545 - TERRACOTTA](../../../../Threat%20Intelligence/Software/Malware/S0545%20-%20TERRACOTTA.md) — [TERRACOTTA](https://attack.mitre.org/software/S0545) has collected the device’s phone number and can check if the active network connection is metered.(Citation: WhiteOps TERRACOTTA) [WhiteOps TERRACOTTA](https://www.whiteops.com/blog/terracotta-android-malware-a-technical-study)
- [S1056 - TianySpy](../../../../Threat%20Intelligence/Software/Malware/S1056%20-%20TianySpy.md) — [TianySpy](https://attack.mitre.org/software/S1056) can check to see if WiFi is enabled.(Citation: trendmicro_tianyspy_0122) [trendmicro_tianyspy_0122](https://www.trendmicro.com/en_us/research/22/a/tianyspy-malware-uses-smishing-disguised-as-message-from-telco.html)
- [S0427 - TrickMo](../../../../Threat%20Intelligence/Software/Malware/S0427%20-%20TrickMo.md) — [TrickMo](https://attack.mitre.org/software/S0427) can collect device network configuration information such as IMSI, IMEI, and Wi-Fi connection state.(Citation: SecurityIntelligence TrickMo) [SecurityIntelligence TrickMo](https://securityintelligence.com/posts/trickbot-pushing-a-2fa-bypass-app-to-bank-customers-in-germany/)
- [S0506 - ViperRAT](../../../../Threat%20Intelligence/Software/Malware/S0506%20-%20ViperRAT.md) — [ViperRAT](https://attack.mitre.org/software/S0506) can collect network configuration data from the device, including phone number, SIM operator, and network operator.(Citation: Lookout ViperRAT) [Lookout ViperRAT](https://blog.lookout.com/viperrat-mobile-apt)

## Detection strategies

- [DET0708 - Detection of Internet Connection Discovery](../../../../Defenses/Detection%20Strategies/DET0708%20-%20Detection%20of%20Internet%20Connection%20Discovery.md)

## Mitigations

- [M1009 - Encrypt Network Traffic](../../../../Defenses/Mitigations/M1009%20-%20Encrypt%20Network%20Traffic.md) — Ensure that traffic is encrypted to reduce adversaries’ ability to intercept, decrypt and manipulate traffic.

## Sources

- [adb_commands](https://gist.github.com/Pulimet/5013acf2cd5b28e55036c82c91bd56d8)
