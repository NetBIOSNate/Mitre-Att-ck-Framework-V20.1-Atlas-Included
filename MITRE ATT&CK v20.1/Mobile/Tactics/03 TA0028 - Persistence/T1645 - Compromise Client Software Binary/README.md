# T1645 - Compromise Client Software Binary

[Mobile](../../../README.md) / [Persistence](../README.md)

Adversaries may modify system software binaries to establish persistent access to devices. System software binaries are used by the underlying operating system and users over adb or terminal emulators. 

Adversaries may make modifications to client software binaries to carry out malicious tasks when those binaries are executed. For example, malware may come with a pre-compiled malicious binary intended to overwrite the genuine one on the device. Since these binaries may be routinely executed by the system or user, the adversary can leverage this for persistent access to the device.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1645)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S0293 - BrainTest](../../../Threat%20Intelligence/Software/Malware/S0293%20-%20BrainTest.md) — [BrainTest](https://attack.mitre.org/software/S0293) uses root privileges (if available) to copy an additional Android app package (APK) to /system/priv-app to maintain persistence even after a factory reset.(Citation: Lookout-BrainTest) [Lookout-BrainTest](https://blog.lookout.com/blog/2016/01/06/brain-test-re-emerges/)
- [S0655 - BusyGasper](../../../Threat%20Intelligence/Software/Malware/S0655%20-%20BusyGasper.md) — [BusyGasper](https://attack.mitre.org/software/S0655) can abuse existing root access to copy components into the system partition.(Citation: SecureList BusyGasper) [SecureList BusyGasper](https://securelist.com/busygasper-the-unfriendly-spy/87627/)
- [S0550 - DoubleAgent](../../../Threat%20Intelligence/Software/Malware/S0550%20-%20DoubleAgent.md) — [DoubleAgent](https://attack.mitre.org/software/S0550) has used exploits to root devices and install additional malware on the system partition.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S0407 - Monokle](../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can remount the system partition as read/write to install attacker-specified certificates.(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)
- [S0316 - Pegasus for Android](../../../Threat%20Intelligence/Software/Malware/S0316%20-%20Pegasus%20for%20Android.md) — [Pegasus for Android](https://attack.mitre.org/software/S0316) attempts to modify the device's system partition.(Citation: Lookout-PegasusAndroid) [Lookout-PegasusAndroid](https://blog.lookout.com/blog/2017/04/03/pegasus-android/)
- [S0289 - Pegasus for iOS](../../../Threat%20Intelligence/Software/Malware/S0289%20-%20Pegasus%20for%20iOS.md) — [Pegasus for iOS](https://attack.mitre.org/software/S0289) modifies the system partition to maintain persistence.(Citation: Lookout-Pegasus) [Lookout-Pegasus](https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf)
- [S0294 - ShiftyBug](../../../Threat%20Intelligence/Software/Malware/S0294%20-%20ShiftyBug.md) — [ShiftyBug](https://attack.mitre.org/software/S0294) is auto-rooting adware that embeds itself as a system application, making it nearly impossible to remove.(Citation: Lookout-Adware) [Lookout-Adware](https://blog.lookout.com/blog/2015/11/04/trojanized-adware/)
- [S0324 - SpyDealer](../../../Threat%20Intelligence/Software/Malware/S0324%20-%20SpyDealer.md) — [SpyDealer](https://attack.mitre.org/software/S0324) maintains persistence by installing an Android application package (APK) on the system partition.(Citation: PaloAlto-SpyDealer) [PaloAlto-SpyDealer](https://researchcenter.paloaltonetworks.com/2017/07/unit42-spydealer-android-trojan-spying-40-apps/)

## Mitigations

- [M1002 - Attestation](../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation could detect devices with unauthorized or unsafe modifications.
- [M1003 - Lock Bootloader](../../../Defenses/Mitigations/M1003%20-%20Lock%20Bootloader.md) — A locked bootloader could prevent unauthorized modifications of protected operating system files.
- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates frequently contain fixes for vulnerabilities that could be leveraged to modify protected operating system files.
- [M1004 - System Partition Integrity](../../../Defenses/Mitigations/M1004%20-%20System%20Partition%20Integrity.md) — Android includes system partition integrity mechanisms that could detect unauthorized modifications.

## Detection strategies

- [DET0712 - Detection of Compromise Client Software Binary](../../../Defenses/Detection%20Strategies/DET0712%20-%20Detection%20of%20Compromise%20Client%20Software%20Binary.md)

## Sources

- [Android-VerifiedBoot](https://source.android.com/security/verifiedboot/)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-27.html)
