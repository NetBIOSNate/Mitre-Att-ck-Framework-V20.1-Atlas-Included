# T1398 - Boot or Logon Initialization Scripts

[Mobile](../../../README.md) / [Persistence](../README.md)

Adversaries may use scripts automatically executed at boot or logon initialization to establish persistence. Initialization scripts are part of the underlying operating system and are not accessible to the user unless the device has been rooted or jailbroken.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1398)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S1095 - AhRat](../../../Threat%20Intelligence/Software/Malware/S1095%20-%20AhRat.md) — [AhRat](https://attack.mitre.org/software/S1095) can register with the `BOOT_COMPLETED` broadcast to start when the device turns on.(Citation: welivesecurity_ahrat_0523) [welivesecurity_ahrat_0523](https://www.welivesecurity.com/2023/05/23/android-app-breaking-bad-legitimate-screen-recording-file-exfiltration/)
- [S1079 - BOULDSPY](../../../Threat%20Intelligence/Software/Malware/S1079%20-%20BOULDSPY.md) — [BOULDSPY](https://attack.mitre.org/software/S1079) can exfiltrate data when the user boots the app, or on device boot.(Citation: lookout_bouldspy_0423) [lookout_bouldspy_0423](https://www.lookout.com/blog/iranian-spyware-bouldspy)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has established auto-start execution during the system boot process.(Citation: Threatfabric LightSpy 2024) [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [S0285 - OldBoot](../../../Threat%20Intelligence/Software/Malware/S0285%20-%20OldBoot.md) — [OldBoot](https://attack.mitre.org/software/S0285) uses escalated privileges to modify the init script on the device's boot partition to maintain persistence.(Citation: HackerNews-OldBoot) [HackerNews-OldBoot](http://thehackernews.com/2014/01/first-widely-distributed-android.html)

## Mitigations

- [M1002 - Attestation](../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation could detect devices with unauthorized or unsafe modifications.
- [M1003 - Lock Bootloader](../../../Defenses/Mitigations/M1003%20-%20Lock%20Bootloader.md) — A locked bootloader could prevent unauthorized modifications to protected operating system files.
- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates frequently contain fixes for vulnerabilities that could be leveraged to modify protected operating system files.
- [M1004 - System Partition Integrity](../../../Defenses/Mitigations/M1004%20-%20System%20Partition%20Integrity.md) — Android and iOS include system partition integrity mechanisms that could detect unauthorized modifications.

## Detection strategies

- [DET0654 - Detection of Boot or Logon Initialization Scripts](../../../Defenses/Detection%20Strategies/DET0654%20-%20Detection%20of%20Boot%20or%20Logon%20Initialization%20Scripts.md)

## Sources

- [Android-VerifiedBoot](https://source.android.com/security/verifiedboot/)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-26.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-27.html)
