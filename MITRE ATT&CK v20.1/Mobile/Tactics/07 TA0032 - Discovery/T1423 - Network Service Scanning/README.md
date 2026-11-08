# T1423 - Network Service Scanning

[Mobile](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to get a listing of services running on remote hosts, including those that may be vulnerable to remote software exploitation. Methods to acquire this information include port scans and vulnerability scans from the mobile device. This technique may take advantage of the mobile device's access to an internal enterprise network either through local connectivity or through a Virtual Private Network (VPN).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1423)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Detection strategies

- [DET0696 - Detection of Network Service Scanning](../../../Defenses/Detection%20Strategies/DET0696%20-%20Detection%20of%20Network%20Service%20Scanning.md)

## Procedure examples

- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) uses the `landevices` module to enumerate devices on the same WiFi network through active scanning.(Citation: Threatfabric LightSpy 2024)(Citation: LinkedIn Dmitry LightSpy 2025)(Citation: Shoshin_Kaspersky LightSpy 2020) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [Shoshin_Kaspersky LightSpy 2020](https://usa.kaspersky.com/blog/lightspy-watering-hole-attack/21301/) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
