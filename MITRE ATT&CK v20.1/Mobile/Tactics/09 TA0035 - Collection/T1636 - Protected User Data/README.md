# T1636 - Protected User Data

[Mobile](../../../README.md) / [Collection](../README.md)

Adversaries may utilize standard operating system APIs to collect data from permission-backed data stores on a device, such as the calendar or contact list. These permissions need to be declared ahead of time. On Android, they must be included in the application’s manifest. On iOS, they must be included in the application’s `Info.plist` file.  

 

In almost all cases, the user is required to grant access to the data store that the application is trying to access. In recent OS versions, vendors have introduced additional privacy controls for users, such as the ability to grant permission to an application only while the application is being actively used by the user. 

 

If the device has been jailbroken or rooted, an adversary may be able to access [Protected User Data](https://attack.mitre.org/techniques/T1636) without the user’s knowledge or approval.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1636)

**Tactics**  [Collection](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1636.005 - Accounts](T1636.005%20-%20Accounts/README.md)
- [T1636.001 - Calendar Entries](T1636.001%20-%20Calendar%20Entries/README.md)
- [T1636.002 - Call Log](T1636.002%20-%20Call%20Log/README.md)
- [T1636.003 - Contact List](T1636.003%20-%20Contact%20List/README.md)
- [T1636.004 - SMS Messages](T1636.004%20-%20SMS%20Messages/README.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — OS feature updates often enhance security and privacy around permissions.
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be taught the danger behind granting unnecessary permissions to an application and should be advised to use extra scrutiny when an application requests them.

## Detection strategies

- [DET0681 - Detection of Protected User Data](../../../Defenses/Detection%20Strategies/DET0681%20-%20Detection%20of%20Protected%20User%20Data.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-13.html)
