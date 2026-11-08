# T1430.001 - Remote Device Management Services

[Mobile](../../../../README.md) / [Collection](../../README.md) / [T1430 - Location Tracking](../README.md)

An adversary may use access to cloud services (e.g. Google's Android Device Manager or Apple iCloud's Find my iPhone) or to an enterprise mobility management (EMM)/mobile device management (MDM) server console to track the location of mobile devices managed by the service.(Citation: Krebs-Location)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1430/001)

**Tactics**  [Discovery](../../../07%20TA0032%20-%20Discovery/README.md), [Collection](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Detection strategies

- [DET0702 - Detection of Remote Device Management Services](../../../../Defenses/Detection%20Strategies/DET0702%20-%20Detection%20of%20Remote%20Device%20Management%20Services.md)

## Mitigations

- [M1012 - Enterprise Policy](../../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — If devices are enrolled using Apple User Enrollment or using a profile owner enrollment mode for Android, device controls prevent the enterprise from accessing the device’s physical location. This is typically used for a Bring Your Own Device (BYOD) deployment.
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should protect their account credentials and enable multi-factor authentication options when available.

## Sources

- [Krebs-Location](https://krebsonsecurity.com/2018/05/tracking-firm-locationsmart-leaked-location-data-for-customers-of-all-major-u-s-mobile-carriers-in-real-time-via-its-web-site/)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-5.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/emm-threats/EMM-7.html)
