# T1629 - Impair Defenses

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may maliciously modify components of a victim environment in order to hinder or disable defensive mechanisms. This not only involves impairing preventative defenses, such as anti-virus, but also detection capabilities that defenders can use to audit activity and identify malicious behavior. This may span both native defenses as well as supplemental capabilities installed by users or mobile endpoint administrators.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1629)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Sub-techniques

- [T1629.002 - Device Lockout](T1629.002%20-%20Device%20Lockout/README.md)
- [T1629.003 - Disable or Modify Tools](T1629.003%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1629.001 - Prevent Application Removal](T1629.001%20-%20Prevent%20Application%20Removal/README.md)

## Procedure examples

- [S1225 - CherryBlos](../../../Threat%20Intelligence/Software/Malware/S1225%20-%20CherryBlos.md) — [CherryBlos](https://attack.mitre.org/software/S1225) has sent the victim back to the home screen when the victim navigates to the malicious application's settings and has automatically approved any permission requests by clicking on the "Allow" button when a system dialogue appears.(Citation: TrendMicro_CherryBlos_July2023) [TrendMicro_CherryBlos_July2023](https://www.trendmicro.com/en_us/research/23/g/cherryblos-and-faketrade-android-malware-involved-in-scam-campai.html)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has intercepted API returns from banking apps that detect malicious services, and modifies the methods to return back an empty list hiding the presence of the malware and other active services.(Citation: ZimperiumOrtegaPratapagiri_GodFather_Jun2025) [ZimperiumOrtegaPratapagiri_GodFather_Jun2025](https://zimperium.com/blog/your-mobile-app-their-playground-the-dark-side-of-the-virtualization)

## Detection strategies

- [DET0687 - Detection of Impair Defenses](../../../Defenses/Detection%20Strategies/DET0687%20-%20Detection%20of%20Impair%20Defenses.md)

## Mitigations

- [M1010 - Deploy Compromised Device Detection Method](../../../Defenses/Mitigations/M1010%20-%20Deploy%20Compromised%20Device%20Detection%20Method.md) — Mobile security software can typically detect if a device has been rooted or jailbroken and can inform the user, who can then take appropriate action.
- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — An EMM/MDM can use the Android `DevicePolicyManager.setPermittedAccessibilityServices` method to set an explicit list of applications that are allowed to use Android's accessibility features.
- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates often contain patches for vulnerabilities that could be exploited for root access. Root access is often a requirement to impairing defenses.
- [M1004 - System Partition Integrity](../../../Defenses/Mitigations/M1004%20-%20System%20Partition%20Integrity.md) — System partition integrity mechanisms, such as Verified Boot, can detect the unauthorized modification of system files.
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Providing user guidance around commonly abused features, such as the modal that requests for administrator permissions, should aid in preventing impairing defenses.

## Sources

- [Samsung Knox Mobile Threat Defense](https://partner.samsungknox.com/mtd)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-22.html)
