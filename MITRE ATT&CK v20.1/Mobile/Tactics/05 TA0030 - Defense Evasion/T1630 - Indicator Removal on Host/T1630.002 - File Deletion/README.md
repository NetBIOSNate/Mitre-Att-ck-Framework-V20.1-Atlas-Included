# T1630.002 - File Deletion

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1630 - Indicator Removal on Host](../README.md)

Adversaries may wipe a device or delete individual files in order to manipulate external outcomes or hide activity. An application must have administrator access to fully wipe the device, while individual files may not require special permissions to delete depending on their storage location.(Citation: Android DevicePolicyManager 2019) 

Stored data could include a variety of file formats, such as Office files, databases, stored emails, and custom file formats. The impact file deletion will have depends on the type of data as well as the goals and objectives of the adversary, but can include deleting update files to evade detection or deleting attacker-specified files for impact.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1630/002)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Mitigations

- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be trained on what device administrator permission request prompts look like, and how to avoid granting permissions on phishing popups.

## Detection strategies

- [DET0638 - Detection of File Deletion](../../../../Defenses/Detection%20Strategies/DET0638%20-%20Detection%20of%20File%20Deletion.md)

## Procedure examples

- [S0440 - Agent Smith](../../../../Threat%20Intelligence/Software/Malware/S0440%20-%20Agent%20Smith.md) — [Agent Smith](https://attack.mitre.org/software/S0440) deletes infected applications’ update packages when they are detected on the system, preventing updates.(Citation: CheckPoint Agent Smith) [CheckPoint Agent Smith](https://research.checkpoint.com/2019/agent-smith-a-new-species-of-mobile-malware/)
- [S1215 - Binary Validator](../../../../Threat%20Intelligence/Software/Malware/S1215%20-%20Binary%20Validator.md) — [Binary Validator](https://attack.mitre.org/software/S1215) has deleted crash logs which may have been created during the initial exploitation phase stored in `/private/var/mobile/Library/Logs/CrashReporter`.(Citation: SecureList OpTriangulation 23Oct2023) [SecureList OpTriangulation 23Oct2023](https://securelist.com/triangulation-validators-modules/110847/)
- [S0529 - CarbonSteal](../../../../Threat%20Intelligence/Software/Malware/S0529%20-%20CarbonSteal.md) — [CarbonSteal](https://attack.mitre.org/software/S0529) has deleted call log entries coming from known C2 sources.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S0505 - Desert Scorpion](../../../../Threat%20Intelligence/Software/Malware/S0505%20-%20Desert%20Scorpion.md) — [Desert Scorpion](https://attack.mitre.org/software/S0505) can delete copies of itself if additional APKs are downloaded to external storage.(Citation: Lookout Desert Scorpion) [Lookout Desert Scorpion](https://blog.lookout.com/desert-scorpion-google-play)
- [S9005 - DocSwap](../../../../Threat%20Intelligence/Software/Malware/S9005%20-%20DocSwap.md) — [DocSwap](https://attack.mitre.org/software/S9005) has the ability to delete files and directories.(Citation: EnkiWhiteHat_KimsukyDOCSWAP_Dec2025)(Citation: S2W_DocSwap_Mar2025) [EnkiWhiteHat_KimsukyDOCSWAP_Dec2025](https://www.enki.co.kr/en/media-center/blog/kimsuky-distributing-malicious-mobile-app-via-qr-code) · [S2W_DocSwap_Mar2025](https://medium.com/s2wblog/detailed-analysis-of-docswap-malware-disguised-as-security-document-viewer-218a728c36ff)
- [S0550 - DoubleAgent](../../../../Threat%20Intelligence/Software/Malware/S0550%20-%20DoubleAgent.md) — [DoubleAgent](https://attack.mitre.org/software/S0550) has deleted or renamed specific files.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S1080 - Fakecalls](../../../../Threat%20Intelligence/Software/Malware/S1080%20-%20Fakecalls.md) — [Fakecalls](https://attack.mitre.org/software/S1080) can manipulate a device’s call log, including deleting incoming calls.(Citation: kaspersky_fakecalls_0422) [kaspersky_fakecalls_0422](https://www.kaspersky.com/blog/fakecalls-banking-trojan/44072/)
- [S0408 - FlexiSpy](../../../../Threat%20Intelligence/Software/Tools/S0408%20-%20FlexiSpy.md) — [FlexiSpy](https://attack.mitre.org/software/S0408) can delete data from a compromised device.(Citation: CyberMerchants-FlexiSpy) [CyberMerchants-FlexiSpy](http://www.cybermerchantsofdeath.com/blog/2017/04/22/FlexiSpy.html)
- [S0421 - GolfSpy](../../../../Threat%20Intelligence/Software/Malware/S0421%20-%20GolfSpy.md) — [GolfSpy](https://attack.mitre.org/software/S0421) can delete arbitrary files on the device.(Citation: Trend Micro Bouncing Golf 2019) [Trend Micro Bouncing Golf 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/mobile-cyberespionage-campaign-bouncing-golf-affects-middle-east/)
- [S0536 - GPlayed](../../../../Threat%20Intelligence/Software/Malware/S0536%20-%20GPlayed.md) — [GPlayed](https://attack.mitre.org/software/S0536) can wipe the device.(Citation: Talos GPlayed) [Talos GPlayed](https://blog.talosintelligence.com/2018/10/gplayedtrojan.html)
- [S1077 - Hornbill](../../../../Threat%20Intelligence/Software/Malware/S1077%20-%20Hornbill.md) — [Hornbill](https://attack.mitre.org/software/S1077) can delete locally gathered files after uploading them to the C2 to avoid suspicion.(Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)
- [S0485 - Mandrake](../../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) can delete all data from an infected device.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0407 - Monokle](../../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can delete arbitrary files on the device, and can also uninstall itself and clean up staging files.(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)
- [C0054 - Operation Triangulation](../../../../Threat%20Intelligence/Campaigns/C0054%20-%20Operation%20Triangulation.md) — During [Operation Triangulation](https://attack.mitre.org/campaigns/C0054), the threat actors removed files from the device.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)
- [S0399 - Pallas](../../../../Threat%20Intelligence/Software/Malware/S0399%20-%20Pallas.md) — [Pallas](https://attack.mitre.org/software/S0399) has the ability to delete attacker-specified files from compromised devices.(Citation: Lookout Dark Caracal Jan 2018) [Lookout Dark Caracal Jan 2018](https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf)
- [S0549 - SilkBean](../../../../Threat%20Intelligence/Software/Malware/S0549%20-%20SilkBean.md) — [SilkBean](https://attack.mitre.org/software/S0549) can delete various piece of device data, such as contacts, call logs, applications, SMS messages, email, plugins, and files in external storage.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S0558 - Tiktok Pro](../../../../Threat%20Intelligence/Software/Malware/S0558%20-%20Tiktok%20Pro.md) — [Tiktok Pro](https://attack.mitre.org/software/S0558) can delete attacker-specified files.(Citation: Zscaler TikTok Spyware) [Zscaler TikTok Spyware](https://www.zscaler.com/blogs/security-research/tiktok-spyware)
- [S1216 - TriangleDB](../../../../Threat%20Intelligence/Software/Malware/S1216%20-%20TriangleDB.md) — [TriangleDB](https://attack.mitre.org/software/S1216) has deleted an implant module or specified files.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)
- [S0418 - ViceLeaker](../../../../Threat%20Intelligence/Software/Malware/S0418%20-%20ViceLeaker.md) — [ViceLeaker](https://attack.mitre.org/software/S0418) can delete arbitrary files from the device.(Citation: SecureList - ViceLeaker 2019) [SecureList - ViceLeaker 2019](https://securelist.com/fanning-the-flames-viceleaker-operation/90877/)
- [S0489 - WolfRAT](../../../../Threat%20Intelligence/Software/Malware/S0489%20-%20WolfRAT.md) — [WolfRAT](https://attack.mitre.org/software/S0489) can delete files from the device.(Citation: Talos-WolfRAT) [Talos-WolfRAT](https://blog.talosintelligence.com/2020/05/the-wolf-is-back.html)

## Sources

- [Android DevicePolicyManager 2019](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html)
