# T1655 - Masquerading

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may attempt to manipulate features of their artifacts to make them appear legitimate or benign to users and/or security tools. Masquerading occurs when the name, location, or appearance of an object, legitimate or malicious, is manipulated or abused for the sake of evading defenses and observation. This may include manipulating file metadata, tricking users into misidentifying the file type, and giving legitimate task or service names.

Renaming abusable system utilities to evade security monitoring is also a form of [Masquerading](https://attack.mitre.org/techniques/T1655)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1655)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1655.001 - Match Legitimate Name or Location](T1655.001%20-%20Match%20Legitimate%20Name%20or%20Location/README.md)

## Procedure examples

- [S1225 - CherryBlos](../../../Threat%20Intelligence/Software/Malware/S1225%20-%20CherryBlos.md) — [CherryBlos](https://attack.mitre.org/software/S1225) has displayed masqueraded wallet applications if the EnabledUIMode field is set to `true`. [CherryBlos](https://attack.mitre.org/software/S1225) has also displayed a fake user interface while victims make withdrawals in the legitimate Binance application if the EnableExchange field is set to `true`. The withdrawal transaction is ultimately transferred to the threat actor’s controlled address.(Citation: TrendMicro_CherryBlos_July2023) [TrendMicro_CherryBlos_July2023](https://www.trendmicro.com/en_us/research/23/g/cherryblos-and-faketrade-android-malware-involved-in-scam-campai.html)
- [S9004 - Crocodilus](../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) has masqueraded as legitimate applications to include applications related to financial institutions, cryptocurrency, gambling, browser updates and occasionally geo-specific themes.(Citation: ThreatFabric_Crocodilus_June2025) [ThreatFabric_Crocodilus_June2025](https://www.threatfabric.com/blogs/crocodilus-mobile-malware-evolving-fast-going-global)
- [S1208 - FjordPhantom](../../../Threat%20Intelligence/Software/Malware/S1208%20-%20FjordPhantom.md) — [FjordPhantom](https://attack.mitre.org/software/S1208) has masqueraded as legitimate banking applications.(Citation: Promon FjordPhantom Oct2024) [Promon FjordPhantom Oct2024](https://promon.io/security-news/fjordphantom-android-malware)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has masqueraded a Mach-O executable as a png file.(Citation: Threatfabric LightSpy 2024)(Citation: LinkedIn Dmitry LightSpy 2025) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [S9006 - VajraSpy](../../../Threat%20Intelligence/Software/Malware/S9006%20-%20VajraSpy.md) — [VajraSpy](https://attack.mitre.org/software/S9006) has masqueraded as messaging and news applications.(Citation: ESET_VajraSpy_Feb2024)(Citation: K7Dhanalakshmi_VajraSpy_April2022) [K7Dhanalakshmi_VajraSpy_April2022](https://labs.k7computing.com/index.php/vajraspy-an-android-rat/) · [ESET_VajraSpy_Feb2024](https://www.welivesecurity.com/en/eset-research/vajraspy-patchwork-espionage-apps/)

## Detection strategies

- [DET0715 - Detection of Masquerading](../../../Defenses/Detection%20Strategies/DET0715%20-%20Detection%20of%20Masquerading.md)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be encouraged to only install apps from authorized app stores, which are less likely to contain malicious repackaged apps.

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-14.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-31.html)
