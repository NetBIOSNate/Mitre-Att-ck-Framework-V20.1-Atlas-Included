# T1632 - Subvert Trust Controls

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may undermine security controls that will either warn users of untrusted activity or prevent execution of untrusted applications. Operating systems and security products may contain mechanisms to identify programs or websites as possessing some level of trust. Examples of such features include: an app being allowed to run because it is signed by a valid code signing certificate; an OS prompt alerting the user that an app came from an untrusted source; or getting an indication that you are about to connect to an untrusted site. The method adversaries use will depend on the specific mechanism they seek to subvert.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1632)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1632.001 - Code Signing Policy Modification](T1632.001%20-%20Code%20Signing%20Policy%20Modification/README.md)

## Detection strategies

- [DET0657 - Detection of Subvert Trust Controls](../../../Defenses/Detection%20Strategies/DET0657%20-%20Detection%20of%20Subvert%20Trust%20Controls.md)

## Mitigations

- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — On iOS, the `allowEnterpriseAppTrust` and `allowEnterpriseAppTrustModification` configuration profile restrictions can be used to prevent users from installing apps signed using enterprise distribution keys.
- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Mobile OSes have implemented measures to make it more difficult to trick users into installing untrusted certificates and configurations. iOS 10.3 and higher add an additional step for users to install new trusted CA certificates and configuration profiles. On Android, apps that target compatibility with Android 7 and higher (API Level 24) default to only trusting CA certificates that are bundled with the operating system, not CA certificates that are added by the user or administrator, hence decreasing their susceptibility to successful adversary-in-the-middle attack.(Citation: Symantec-iOSProfile2)(Citation: Android-TrustedCA) [Symantec-iOSProfile2](https://www.symantec.com/connect/blogs/apple-ios-103-finally-battles-malicious-profiles) · [Android-TrustedCA](https://android-developers.googleblog.com/2016/07/changes-to-trusted-certificate.html)
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Typically, insecure or malicious configuration settings are not installed without the user's consent. Users should be advised not to install unexpected configuration settings (CA certificates, iOS Configuration Profiles, Mobile Device Management server provisioning).

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/stack-threats/STA-7.html)
