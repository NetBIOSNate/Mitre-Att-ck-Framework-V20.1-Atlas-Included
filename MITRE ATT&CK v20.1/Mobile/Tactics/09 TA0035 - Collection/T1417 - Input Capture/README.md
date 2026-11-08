# T1417 - Input Capture

[Mobile](../../../README.md) / [Collection](../README.md)

Adversaries may use methods of capturing user input to obtain credentials or collect information. During normal device usage, users often provide credentials to various locations, such as login pages/portals or system dialog boxes. Input capture mechanisms may be transparent to the user (e.g. [Keylogging](https://attack.mitre.org/techniques/T1417/001)) or rely on deceiving the user into providing input into what they believe to be a genuine application prompt (e.g. [GUI Input Capture](https://attack.mitre.org/techniques/T1417/002)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1417)

**Tactics**  [Credential Access](../../06%20TA0031%20-%20Credential%20Access/README.md), [Collection](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1417.002 - GUI Input Capture](T1417.002%20-%20GUI%20Input%20Capture/README.md)
- [T1417.001 - Keylogging](T1417.001%20-%20Keylogging/README.md)

## Mitigations

- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — When using Samsung Knox, third-party keyboards must be explicitly added to an allow list in order to be available to the end-user.(Citation: Samsung Keyboards) An EMM/MDM can use the Android `DevicePolicyManager.setPermittedAccessibilityServices` method to set an explicit list of applications that are allowed to use Android's accessibility features. [Samsung Keyboards](https://web.archive.org/web/20201112021547/https://support.samsungknox.com/hc/en-us/articles/360001485027-3rd-party-keyboards-must-be-whitelisted-)
- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — The `HIDE_OVERLAY_WINDOWS` permission was introduced in Android 12 allowing apps to hide overlay windows of type `TYPE_APPLICATION_OVERLAY` drawn by other apps with the `SYSTEM_ALERT_WINDOW` permission, preventing other applications from creating overlay windows on top of the current application.(Citation: Android 12 Features) [Android 12 Features](https://developer.android.com/about/versions/12/features)
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be wary of granting applications dangerous or privacy-intrusive permissions, such as keyboard registration or accessibility service access.

## Procedure examples

- [S1225 - CherryBlos](../../../Threat%20Intelligence/Software/Malware/S1225%20-%20CherryBlos.md) — [CherryBlos](https://attack.mitre.org/software/S1225) has captured victims' credentials through predefined fake activities.(Citation: TrendMicro_CherryBlos_July2023) [TrendMicro_CherryBlos_July2023](https://www.trendmicro.com/en_us/research/23/g/cherryblos-and-faketrade-android-malware-involved-in-scam-campai.html)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has the captured information about the device's screen to include detailed tap events.(Citation: ZimperiumOrtegaPratapagiri_GodFather_Jun2025) [ZimperiumOrtegaPratapagiri_GodFather_Jun2025](https://zimperium.com/blog/your-mobile-app-their-playground-the-dark-side-of-the-virtualization)
- [S1126 - Phenakite](../../../Threat%20Intelligence/Software/Malware/S1126%20-%20Phenakite.md) — [Phenakite](https://attack.mitre.org/software/S1126) has used phishing sites for iCloud and Facebook if either of those were used for authentication during the chat sign up process.(Citation: fb_arid_viper) [fb_arid_viper](https://web.archive.org/web/20231126111812/https:/about.fb.com/wp-content/uploads/2021/04/Technical-threat-report-Arid-Viper-April-2021.pdf)

## Detection strategies

- [DET0705 - Detection of Input Capture](../../../Defenses/Detection%20Strategies/DET0705%20-%20Detection%20of%20Input%20Capture.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-31.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/authentication-threats/AUT-13.html)
