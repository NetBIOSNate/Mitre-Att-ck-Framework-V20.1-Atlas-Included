# T1424 - Process Discovery

[Mobile](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to get information about running processes on a device. Information obtained could be used to gain an understanding of common software/applications running on devices within a network. Adversaries may use the information from [Process Discovery](https://attack.mitre.org/techniques/T1424) during automated discovery to shape follow-on behaviors, including whether or not the adversary fully infects the target and/or attempts specific actions. 

 

Recent Android security enhancements have made it more difficult to obtain a list of running processes. On Android 7 and later, there is no way for an application to obtain the process list without abusing elevated privileges. This is due to the Android kernel utilizing the `hidepid` mount feature. Prior to Android 7, applications could utilize the `ps` command or examine the `/proc` directory on the device.(Citation: Android-SELinuxChanges) 

 

In iOS, applications have previously been able to use the `sysctl` command to obtain a list of running processes. This functionality has been removed in later iOS versions.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1424)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Mitigations

- [M1002 - Attestation](../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Attestation can typically detect rooted devices. For MDM-enrolled devices, action can be taken if a device fails an attestation check.
- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 7 and later iOS versions introduced changes that prevent applications from performing Process Discovery without elevated privileges.

## Procedure examples

- [S0440 - Agent Smith](../../../Threat%20Intelligence/Software/Malware/S0440%20-%20Agent%20Smith.md) — [Agent Smith](https://attack.mitre.org/software/S0440) checks if a targeted application is running in user-space prior to infection.(Citation: CheckPoint Agent Smith) [CheckPoint Agent Smith](https://research.checkpoint.com/2019/agent-smith-a-new-species-of-mobile-malware/)
- [S0422 - Anubis](../../../Threat%20Intelligence/Software/Malware/S0422%20-%20Anubis.md) — [Anubis](https://attack.mitre.org/software/S0422) can collect a list of running processes.(Citation: Zimperium z9) [Zimperium z9](https://blog.zimperium.com/how-zimperiums-z9-detected-unknown-mobile-malware-overlooked-by-the-av-industry/)
- [S1215 - Binary Validator](../../../Threat%20Intelligence/Software/Malware/S1215%20-%20Binary%20Validator.md) — [Binary Validator](https://attack.mitre.org/software/S1215) has obtained a list of running processes.(Citation: SecureList OpTriangulation 23Oct2023) [SecureList OpTriangulation 23Oct2023](https://securelist.com/triangulation-validators-modules/110847/)
- [S1225 - CherryBlos](../../../Threat%20Intelligence/Software/Malware/S1225%20-%20CherryBlos.md) — [CherryBlos](https://attack.mitre.org/software/S1225) has used the Accessibility Service to monitor when a wallet application has launched.(Citation: TrendMicro_CherryBlos_July2023) [TrendMicro_CherryBlos_July2023](https://www.trendmicro.com/en_us/research/23/g/cherryblos-and-faketrade-android-malware-involved-in-scam-campai.html)
- [S0421 - GolfSpy](../../../Threat%20Intelligence/Software/Malware/S0421%20-%20GolfSpy.md) — [GolfSpy](https://attack.mitre.org/software/S0421) can obtain a list of running processes.(Citation: Trend Micro Bouncing Golf 2019) [Trend Micro Bouncing Golf 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/mobile-cyberespionage-campaign-bouncing-golf-affects-middle-east/)
- [S0544 - HenBox](../../../Threat%20Intelligence/Software/Malware/S0544%20-%20HenBox.md) — [HenBox](https://attack.mitre.org/software/S0544) can obtain a list of running processes.(Citation: Palo Alto HenBox) [Palo Alto HenBox](https://unit42.paloaltonetworks.com/unit42-henbox-chickens-come-home-roost/)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has collected a list of running processes.(Citation: Threatfabric LightSpy 2024)(Citation: LinkedIn Dmitry LightSpy 2025) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [C0054 - Operation Triangulation](../../../Threat%20Intelligence/Campaigns/C0054%20-%20Operation%20Triangulation.md) — During [Operation Triangulation](https://attack.mitre.org/campaigns/C0054), the threat actors have obtained a list of processes.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)
- [S0411 - Rotexy](../../../Threat%20Intelligence/Software/Malware/S0411%20-%20Rotexy.md) — [Rotexy](https://attack.mitre.org/software/S0411) collects information about running processes.(Citation: securelist rotexy 2018) [securelist rotexy 2018](https://securelist.com/the-rotexy-mobile-trojan-banker-and-ransomware/88893/)
- [S1055 - SharkBot](../../../Threat%20Intelligence/Software/Malware/S1055%20-%20SharkBot.md) — [SharkBot](https://attack.mitre.org/software/S1055) can use Accessibility Services to detect which process is in the foreground.(Citation: nccgroup_sharkbot_0322) [nccgroup_sharkbot_0322](https://research.nccgroup.com/2022/03/03/sharkbot-a-new-generation-android-banking-trojan-being-distributed-on-google-play-store/)
- [S1216 - TriangleDB](../../../Threat%20Intelligence/Software/Malware/S1216%20-%20TriangleDB.md) — [TriangleDB](https://attack.mitre.org/software/S1216) has collected a list of running processes.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)
- [S0489 - WolfRAT](../../../Threat%20Intelligence/Software/Malware/S0489%20-%20WolfRAT.md) — [WolfRAT](https://attack.mitre.org/software/S0489) uses `dumpsys` to determine if certain applications are running.(Citation: Talos-WolfRAT) [Talos-WolfRAT](https://blog.talosintelligence.com/2020/05/the-wolf-is-back.html)
- [S0311 - YiSpecter](../../../Threat%20Intelligence/Software/Malware/S0311%20-%20YiSpecter.md) — [YiSpecter](https://attack.mitre.org/software/S0311) has collected information about running processes.(Citation: paloalto_yispecter_1015) [paloalto_yispecter_1015](https://unit42.paloaltonetworks.com/yispecter-first-ios-malware-attacks-non-jailbroken-ios-devices-by-abusing-private-apis/)

## Detection strategies

- [DET0692 - Detection of Process Discovery](../../../Defenses/Detection%20Strategies/DET0692%20-%20Detection%20of%20Process%20Discovery.md)

## Sources

- [Android-SELinuxChanges](https://code.google.com/p/android/issues/detail?id=205565)
