# T1421 - System Network Connections Discovery

[Mobile](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to get a listing of network connections to or from the compromised device they are currently accessing or from remote systems by querying for information over the network. 

 

This is typically accomplished by utilizing device APIs to collect information about nearby networks, such as Wi-Fi, Bluetooth, and cellular tower connections. On Android, this can be done by querying the respective APIs: 

 

* `WifiInfo` for information about the current Wi-Fi connection, as well as nearby Wi-Fi networks. Querying the `WiFiInfo` API requires the application to hold the `ACCESS_FINE_LOCATION` permission. 

* `BluetoothAdapter` for information about Bluetooth devices, which also requires the application to hold several permissions granted by the user at runtime. 

* For Android versions prior to Q, applications can use the `TelephonyManager.getNeighboringCellInfo()` method. For Q and later, applications can use the `TelephonyManager.getAllCellInfo()` method. Both methods require the application hold the `ACCESS_FINE_LOCATION` permission.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1421)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [C0033 - C0033](../../../Threat%20Intelligence/Campaigns/C0033%20-%20C0033.md) — During [C0033](https://attack.mitre.org/campaigns/C0033), [PROMETHIUM](https://attack.mitre.org/groups/G0056) used [StrongPity](https://attack.mitre.org/software/S0491) to collect information regarding available Wi-Fi networks.(Citation: trendmicro_strongpity) [trendmicro_strongpity](https://www.trendmicro.com/en_za/research/21/g/strongpity-apt-group-deploys-android-malware-for-the-first-time.html)
- [S0405 - Exodus](../../../Threat%20Intelligence/Software/Malware/S0405%20-%20Exodus.md) — [Exodus](https://attack.mitre.org/software/S0405) Two collects a list of nearby base stations.(Citation: SWB Exodus March 2019) [SWB Exodus March 2019](https://web.archive.org/web/20200314194610/https://securitywithoutborders.org/blog/2019/03/29/exodus.html)
- [S0509 - FakeSpy](../../../Threat%20Intelligence/Software/Malware/S0509%20-%20FakeSpy.md) — [FakeSpy](https://attack.mitre.org/software/S0509) can collect the device’s network information.(Citation: Cybereason FakeSpy) [Cybereason FakeSpy](https://www.cybereason.com/blog/fakespy-masquerades-as-postal-service-apps-around-the-world)
- [S0408 - FlexiSpy](../../../Threat%20Intelligence/Software/Tools/S0408%20-%20FlexiSpy.md) — [FlexiSpy](https://attack.mitre.org/software/S0408) can collect a list of known Wi-Fi access points.(Citation: FlexiSpy-Features) [FlexiSpy-Features](https://www.flexispy.com/en/features-overview.htm)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has collected a list of cellular networks and connected Wi-Fi history using a LAN scanner based on MMLanScan.(Citation: FirshSecureList LightSpy 2020)(Citation: MelikovBlackBerry LightSpy 2024)(Citation: Threatfabric LightSpy 2023)(Citation: Threatfabric LightSpy 2024)(Citation: Shoshin_Kaspersky LightSpy 2020) [FirshSecureList LightSpy 2020](https://securelist.com/ios-exploit-chain-deploys-lightspy-malware/96407/) · [MelikovBlackBerry LightSpy 2024](https://blogs.blackberry.com/en/2024/04/lightspy-returns-renewed-espionage-campaign-targets-southern-asia-possibly-india) · [Shoshin_Kaspersky LightSpy 2020](https://usa.kaspersky.com/blog/lightspy-watering-hole-attack/21301/) · [Threatfabric LightSpy 2023](https://www.threatfabric.com/blogs/lightspy-mapt-mobile-payment-system-attack) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [S0407 - Monokle](../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can retrieve nearby cell tower and Wi-Fi network information.(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)
- [S9040 - NGate](../../../Threat%20Intelligence/Software/Malware/S9040%20-%20NGate.md) — [NGate](https://attack.mitre.org/software/S9040) has requested for the `ACCESS_NETWORK_STATE` permission.(Citation: CERTPL_NGate_Nov2025) [CERTPL_NGate_Nov2025](https://cert.pl/en/posts/2025/11/analiza-ngate/)
- [S0399 - Pallas](../../../Threat%20Intelligence/Software/Malware/S0399%20-%20Pallas.md) — [Pallas](https://attack.mitre.org/software/S0399) gathers and exfiltrates data about nearby Wi-Fi access points.(Citation: Lookout Dark Caracal Jan 2018) [Lookout Dark Caracal Jan 2018](https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf)
- [S0289 - Pegasus for iOS](../../../Threat%20Intelligence/Software/Malware/S0289%20-%20Pegasus%20for%20iOS.md) — [Pegasus for iOS](https://attack.mitre.org/software/S0289) monitors the connection state and tracks which types of networks the phone is connected to, potentially to determine the bandwidth and ability to send full data across the network.(Citation: Lookout-Pegasus) [Lookout-Pegasus](https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf)
- [S0506 - ViperRAT](../../../Threat%20Intelligence/Software/Malware/S0506%20-%20ViperRAT.md) — [ViperRAT](https://attack.mitre.org/software/S0506) can collect the device’s cell tower information.(Citation: Lookout ViperRAT) [Lookout ViperRAT](https://blog.lookout.com/viperrat-mobile-apt)

## Detection strategies

- [DET0636 - Detection of System Network Connections Discovery](../../../Defenses/Detection%20Strategies/DET0636%20-%20Detection%20of%20System%20Network%20Connections%20Discovery.md)
