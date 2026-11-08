# DC0115 - Protected Configuration

[Mobile](../../README.md) / [Data Components](README.md)

Protected Configuration represents security-sensitive device settings, security policies, or operating system configurations that are normally restricted to administrators, system services, or device management platforms.
Monitoring these configurations enables detection of adversaries attempting to weaken device security controls or alter trusted device relationships.

Examples
Android:

- USB debugging enabled
- Unknown app installation allowed
- Developer options enabled

iOS:

- Developer mode enabled
- Device pairing trust relationships established
- Configuration profile restrictions modified

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0115)

## Log sources and channels

- **iOS:MDMLog** — profile with payload_type LIKE 'com.apple.security.*' installed where mdm_origin=false — security payload from non-MDM source is the policy modification event
- **android:MDMLog** — Biometric, credential, lockscreen, trust-agent, Smart Lock, or device-admin-related protected device configuration changed
- **android:MDMLog** — Managed Wi-Fi, VPN, cellular, or location-related policy state remains unchanged while network capability degrades
- **android:MDMLog** — Managed storage, backup, enterprise file access, or device policy state remains unchanged while bulk destructive file transformation occurs
- **android:MDMLog** — Managed app catalog, enterprise update policy, or trusted distribution posture remains unchanged while a known app exhibits materially different post-update behavior
- **android:MDMLog** — Managed app distribution, enterprise catalog trust, and update policy remain expected while a known package exhibits materially different post-install or post-update behavior
- **Application Vetting** — None
- **iOS:MDMLog** — Developer Mode enabled, supervised-device restriction changed, or trust-related protected device posture changed
- **iOS:MDMLog** — Passcode, biometrics, attention-aware authentication, or supervised-device lock policy changed in a way that weakens or alters the authentication boundary
- **iOS:MDMLog** — Managed Wi-Fi, VPN, cellular, or location-service policy remains unchanged while device connectivity repeatedly degrades
- **iOS:MDMLog** — Managed app distribution, supervised install posture, or provisioning trust context remains expected while a known app exhibits materially different behavior after version change
- **android:DevicePolicyManager** — DevicePolicyManager policy/compliance/security-state queries and SecurityLog events where supported
- **iOS:MDM** — DeviceInformation / SecurityInfo / ProfileList / restrictions and compliance queries

## Analytics using this component

- [AN1680 - Analytic 1680](../Analytics/AN1680.md)
- [AN1687 - Analytic 1687](../Analytics/AN1687.md)
- [AN1688 - Analytic 1688](../Analytics/AN1688.md)
- [AN1697 - Analytic 1697](../Analytics/AN1697.md)
- [AN1698 - Analytic 1698](../Analytics/AN1698.md)
- [AN1713 - Analytic 1713](../Analytics/AN1713.md)
- [AN1714 - Analytic 1714](../Analytics/AN1714.md)
- [AN1721 - Analytic 1721](../Analytics/AN1721.md)
- [AN1723 - Analytic 1723](../Analytics/AN1723.md)
- [AN1724 - Analytic 1724](../Analytics/AN1724.md)
- [AN1746 - Analytic 1746](../Analytics/AN1746.md)
- [AN1781 - Analytic 1781](../Analytics/AN1781.md)
- [AN1792 - Analytic 1792](../Analytics/AN1792.md)
- [AN1799 - Analytic 1799](../Analytics/AN1799.md)
- [AN1803 - Analytic 1803](../Analytics/AN1803.md)
- [AN1820 - Analytic 1820](../Analytics/AN1820.md)
- [AN1823 - Analytic 1823](../Analytics/AN1823.md)
- [AN1824 - Analytic 1824](../Analytics/AN1824.md)
