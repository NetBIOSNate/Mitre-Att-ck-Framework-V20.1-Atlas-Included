# T1628.001 - Suppress Application Icon

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1628 - Hide Artifacts](../README.md)

A malicious application could suppress its icon from being displayed to the user in the application launcher. This hides the fact that it is installed, and can make it more difficult for the user to uninstall the application. Hiding the application's icon programmatically does not require any special permissions. 

This behavior has been seen in the BankBot/Spy Banker family of malware.(Citation: android-trojan-steals-paypal-2fa)(Citation: sunny-stolen-credentials)(Citation: bankbot-spybanker) 

Beginning in Android 10, changes were introduced to inhibit malicious applications’ ability to hide their icon. If an app is a system app, requests no permissions, or does not have a launcher activity, the application’s icon will be fully hidden. Further, if the device is fully managed or the application is in a work profile, the icon will be fully hidden. Otherwise, a synthesized activity is shown, which is a launcher icon that represents the app’s details page in the system settings. If the user clicks the synthesized activity in the launcher, they are taken to the application’s details page in the system settings.(Citation: Android 10 Limitations to Hiding App Icons)(Citation: LauncherApps getActivityList)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1628/001)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 10 introduced changes to prevent malicious applications from fully suppressing their icon in the launcher.(Citation: Android 10 Limitations to Hiding App Icons)(Citation: LauncherApps getActivityList) [Android 10 Limitations to Hiding App Icons](https://source.android.com/setup/start/android-10-release#limitations_to_hiding_app_icons) · [LauncherApps getActivityList](https://developer.android.com/reference/kotlin/android/content/pm/LauncherApps#getactivitylist)
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be shown what a synthetic activity looks like so they can scrutinize them in the future.

## Procedure examples

- [S0440 - Agent Smith](../../../../Threat%20Intelligence/Software/Malware/S0440%20-%20Agent%20Smith.md) — [Agent Smith](https://attack.mitre.org/software/S0440) can hide its icon from the application launcher.(Citation: CheckPoint Agent Smith) [CheckPoint Agent Smith](https://research.checkpoint.com/2019/agent-smith-a-new-species-of-mobile-malware/)
- [S0525 - Android/AdDisplay.Ashas](../../../../Threat%20Intelligence/Software/Malware/S0525%20-%20Android%20-%20AdDisplay.Ashas.md) — [Android/AdDisplay.Ashas](https://attack.mitre.org/software/S0525) can hide its icon and create a shortcut based on the C2 server response.(Citation: WeLiveSecurity AdDisplayAshas) [WeLiveSecurity AdDisplayAshas](https://www.welivesecurity.com/2019/10/24/tracking-down-developer-android-adware/)
- [S0655 - BusyGasper](../../../../Threat%20Intelligence/Software/Malware/S0655%20-%20BusyGasper.md) — [BusyGasper](https://attack.mitre.org/software/S0655) can hide its icon.(Citation: SecureList BusyGasper) [SecureList BusyGasper](https://securelist.com/busygasper-the-unfriendly-spy/87627/)
- [S0480 - Cerberus](../../../../Threat%20Intelligence/Software/Malware/S0480%20-%20Cerberus.md) — [Cerberus](https://attack.mitre.org/software/S0480) hides its icon from the application drawer after being launched for the first time.(Citation: Threat Fabric Cerberus) [Threat Fabric Cerberus](https://www.threatfabric.com/blogs/cerberus-a-new-banking-trojan-from-the-underworld.html)
- [S0505 - Desert Scorpion](../../../../Threat%20Intelligence/Software/Malware/S0505%20-%20Desert%20Scorpion.md) — [Desert Scorpion](https://attack.mitre.org/software/S0505) can hide its icon.(Citation: Lookout Desert Scorpion) [Lookout Desert Scorpion](https://blog.lookout.com/desert-scorpion-google-play)
- [S0550 - DoubleAgent](../../../../Threat%20Intelligence/Software/Malware/S0550%20-%20DoubleAgent.md) — [DoubleAgent](https://attack.mitre.org/software/S0550) has hidden its app icon.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S1054 - Drinik](../../../../Threat%20Intelligence/Software/Malware/S1054%20-%20Drinik.md) — [Drinik](https://attack.mitre.org/software/S1054) can hide its application icon.(Citation: cyble_drinik_1022) [cyble_drinik_1022](https://web.archive.org/web/20221114031945/https://blog.cyble.com/2022/10/27/drinik-malware-returns-with-advanced-capabilities-targeting-indian-taxpayers/)
- [S0509 - FakeSpy](../../../../Threat%20Intelligence/Software/Malware/S0509%20-%20FakeSpy.md) — [FakeSpy](https://attack.mitre.org/software/S0509) can hide its icon if it detects that it is being run on an emulator.(Citation: Cybereason FakeSpy) [Cybereason FakeSpy](https://www.cybereason.com/blog/fakespy-masquerades-as-postal-service-apps-around-the-world)
- [S0408 - FlexiSpy](../../../../Threat%20Intelligence/Software/Tools/S0408%20-%20FlexiSpy.md) — [FlexiSpy](https://attack.mitre.org/software/S0408) is capable of hiding SuperSU's icon if it is installed and visible.(Citation: FortiGuard-FlexiSpy) [FlexiSpy](https://attack.mitre.org/software/S0408) can also hide its own icon to make detection and the uninstallation process more difficult.(Citation: FlexiSpy-Features) [FlexiSpy-Features](https://www.flexispy.com/en/features-overview.htm) · [FortiGuard-FlexiSpy](https://d3gpjj9d20n0p3.cloudfront.net/fortiguard/research/Dig%20Deep%20into%20FlexiSpy%20for%20Android%28white%20paper%29_KaiLu.pdf)
- [S1103 - FlixOnline](../../../../Threat%20Intelligence/Software/Malware/S1103%20-%20FlixOnline.md) — [FlixOnline](https://attack.mitre.org/software/S1103) can hide its application icon.(Citation: checkpoint_flixonline_0421) [checkpoint_flixonline_0421](https://research.checkpoint.com/2021/new-wormable-android-malware-spreads-by-creating-auto-replies-to-messages-in-whatsapp/)
- [S0423 - Ginp](../../../../Threat%20Intelligence/Software/Malware/S0423%20-%20Ginp.md) — [Ginp](https://attack.mitre.org/software/S0423) hides its icon after installation.(Citation: ThreatFabric Ginp) [ThreatFabric Ginp](https://www.threatfabric.com/blogs/ginp_a_malware_patchwork_borrowing_from_anubis.html)
- [S0406 - Gustuff](../../../../Threat%20Intelligence/Software/Malware/S0406%20-%20Gustuff.md) — [Gustuff](https://attack.mitre.org/software/S0406) hides its icon after installation.(Citation: Group IB Gustuff Mar 2019) [Group IB Gustuff Mar 2019](https://www.group-ib.com/blog/gustuff)
- [S0485 - Mandrake](../../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) can hide its icon on older Android versions.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0411 - Rotexy](../../../../Threat%20Intelligence/Software/Malware/S0411%20-%20Rotexy.md) — [Rotexy](https://attack.mitre.org/software/S0411) hides its icon after first launch.(Citation: securelist rotexy 2018) [securelist rotexy 2018](https://securelist.com/the-rotexy-mobile-trojan-banker-and-ransomware/88893/)
- [S1062 - S.O.V.A.](../../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) can hide its application icon.(Citation: threatfabric_sova_0921) [threatfabric_sova_0921](https://www.threatfabric.com/blogs/sova-new-trojan-with-fowl-intentions.html)
- [S0419 - SimBad](../../../../Threat%20Intelligence/Software/Malware/S0419%20-%20SimBad.md) — [SimBad](https://attack.mitre.org/software/S0419) hides its icon from the application launcher.(Citation: CheckPoint SimBad 2019) [CheckPoint SimBad 2019](https://research.checkpoint.com/simbad-a-rogue-adware-campaign-on-google-play/)
- [S1195 - SpyC23](../../../../Threat%20Intelligence/Software/Malware/S1195%20-%20SpyC23.md) — [SpyC23](https://attack.mitre.org/software/S1195) can hide its icon.(Citation: welivesecurity_apt-c-23) [welivesecurity_apt-c-23](https://web.archive.org/web/20201123042131/www.welivesecurity.com/2020/09/30/aptc23-group-evolves-its-android-spyware/)
- [S0558 - Tiktok Pro](../../../../Threat%20Intelligence/Software/Malware/S0558%20-%20Tiktok%20Pro.md) — [Tiktok Pro](https://attack.mitre.org/software/S0558) can hide its icon after launch.(Citation: Zscaler TikTok Spyware) [Zscaler TikTok Spyware](https://www.zscaler.com/blogs/security-research/tiktok-spyware)
- [S0302 - Twitoor](../../../../Threat%20Intelligence/Software/Malware/S0302%20-%20Twitoor.md) — [Twitoor](https://attack.mitre.org/software/S0302) can hide its presence on the system.(Citation: ESET-Twitoor) [ESET-Twitoor](http://www.welivesecurity.com/2016/08/24/first-twitter-controlled-android-botnet-discovered/)
- [S0418 - ViceLeaker](../../../../Threat%20Intelligence/Software/Malware/S0418%20-%20ViceLeaker.md) — [ViceLeaker](https://attack.mitre.org/software/S0418) includes code to hide its icon, but the function does not appear to be called in an analyzed version of the software.(Citation: Bitdefender - Triout 2018) [Bitdefender - Triout 2018](https://labs.bitdefender.com/2018/08/triout-spyware-framework-for-android-with-extensive-surveillance-capabilities/)
- [S0311 - YiSpecter](../../../../Threat%20Intelligence/Software/Malware/S0311%20-%20YiSpecter.md) — [YiSpecter](https://attack.mitre.org/software/S0311) has hidden the app icon from iOS springboard.(Citation: paloalto_yispecter_1015) [paloalto_yispecter_1015](https://unit42.paloaltonetworks.com/yispecter-first-ios-malware-attacks-non-jailbroken-ios-devices-by-abusing-private-apis/)

## Detection strategies

- [DET0714 - Detection of Suppress Application Icon](../../../../Defenses/Detection%20Strategies/DET0714%20-%20Detection%20of%20Suppress%20Application%20Icon.md)

## Sources

- [Android 10 Limitations to Hiding App Icons](https://source.android.com/setup/start/android-10-release#limitations_to_hiding_app_icons)
- [LauncherApps getActivityList](https://developer.android.com/reference/kotlin/android/content/pm/LauncherApps#getactivitylist)
- [sunny-stolen-credentials](https://www.welivesecurity.com/2017/02/22/sunny-chance-stolen-credentials-malicious-weather-app-found-google-play/)
- [android-trojan-steals-paypal-2fa](https://www.welivesecurity.com/2018/12/11/android-trojan-steals-money-paypal-accounts-2fa/)
- [bankbot-spybanker](https://www.cyber.nj.gov/threat-landscape/malware/trojans/bankbot-spy-banker)
