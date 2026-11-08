# T1625.001 - System Runtime API Hijacking

[Mobile](../../../../README.md) / [Persistence](../../README.md) / [T1625 - Hijack Execution Flow](../README.md)

Adversaries may execute their own malicious payloads by hijacking the way an operating system runs applications. Hijacking execution flow can be for the purposes of persistence since this hijacked execution may reoccur at later points in time. 


On Android, adversaries may overwrite the standard OS API library with a malicious alternative to hook into core functions to achieve persistence. By doing this, the adversary’s code will be executed every time the overwritten API function is called by an app on the infected device.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1625/001)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Procedure examples

- [S0420 - Dvmap](../../../../Threat%20Intelligence/Software/Malware/S0420%20-%20Dvmap.md) — [Dvmap](https://attack.mitre.org/software/S0420) replaces `/system/bin/ip` with a malicious version. [Dvmap](https://attack.mitre.org/software/S0420) can inject code by patching `libdmv.so` or `libandroid_runtime.so`, depending on the Android OS version. Both libraries are related to the Dalvik and ART runtime environments. The patched functions can only call `/system/bin/ip`, which was replaced with the malicious version.(Citation: SecureList DVMap June 2017) [SecureList DVMap June 2017](https://securelist.com/dvmap-the-first-android-malware-with-code-injection/78648/)
- [S0408 - FlexiSpy](../../../../Threat%20Intelligence/Software/Tools/S0408%20-%20FlexiSpy.md) — [FlexiSpy](https://attack.mitre.org/software/S0408) installs boot hooks into `/system/su.d`.(Citation: FortiGuard-FlexiSpy) [FortiGuard-FlexiSpy](https://d3gpjj9d20n0p3.cloudfront.net/fortiguard/research/Dig%20Deep%20into%20FlexiSpy%20for%20Android%28white%20paper%29_KaiLu.pdf)
- [S0494 - Zen](../../../../Threat%20Intelligence/Software/Malware/S0494%20-%20Zen.md) — [Zen](https://attack.mitre.org/software/S0494) can install itself on the system partition to achieve persistence. [Zen](https://attack.mitre.org/software/S0494) can also replace `framework.jar`, which allows it to intercept and modify the behavior of the standard Android API.(Citation: Google Security Zen) [Google Security Zen](https://security.googleblog.com/2019/01/pha-family-highlights-zen-and-its.html)

## Detection strategies

- [DET0689 - Detection of System Runtime API Hijacking](../../../../Defenses/Detection%20Strategies/DET0689%20-%20Detection%20of%20System%20Runtime%20API%20Hijacking.md)

## Mitigations

- [M1002 - Attestation](../../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation could detect unauthorized operating system modifications.
- [M1004 - System Partition Integrity](../../../../Defenses/Mitigations/M1004%20-%20System%20Partition%20Integrity.md) — Android Verified Boot can detect unauthorized modifications made to the system partition, which could lead to execution flow hijacking.(Citation: Android-VerifiedBoot) [Android-VerifiedBoot](https://source.android.com/security/verifiedboot/)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-27.html)
