# DC0118 - System Settings

[Mobile](../../README.md) / [Data Components](README.md)

System Settings represent user-visible or OS-level configuration settings that influence device behavior, application permissions, connectivity, or system features.

Monitoring system settings changes allows defenders to detect abnormal modifications that may indicate malicious activity or device compromise.


Collection Methods

- MDM device telemetry
- Mobile EDR monitoring
- OS configuration monitoring

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0118)

## Log sources and channels

- **android:DevicePolicyManager** — Managed security state and policy information, including supported installation-related settings
- **android:DevicePolicyManager** — DevicePolicyManager policy/compliance/security-state queries and SecurityLog events where supported
- **android:MDMLog** — device USB mode change (charging to file transfer / debugging / accessory)
- **android:MDMLog** — Application or service remains active, foregrounds, or overlays during device locked state or immediately at unlock transition with weak recent user interaction context
- **android:MDMLog** — No user-initiated airplane mode, radio disablement, or managed network setting change occurred during repeated connectivity degradation
- **iOS:MDM** — DeviceInformation / SecurityInfo / ProfileList / restrictions and compliance queries
- **iOS:MDMLog** — Trusted computer / host relationship established or relevant device trust setting changed
- **iOS:MDMLog** — No user-initiated airplane mode or radio-related setting change occurred while applications experience repeated network unavailability
- **MobileEDR:telemetry** — Settings.Secure/Global write to install_unknown_apps=1 by process NOT IN MDMAgentPackageList + PackageInstaller call with unknown cert within TimeWindow where MDM agent is the only authorized settings writer
- **MobileEDR:telemetry** — Microphone sensor activation or audio recording session initiated by application process
- **MobileEDR:telemetry** — Application transitions to background or executes while screen locked during microphone session
- **MobileEDR:telemetry** — Cellular service state transitions (in-service→no-service), SIM state change, carrier/operator identifier change, or baseband/telephony stack state change observed by agent telemetry
- **MobileEDR:telemetry** — Application remains backgrounded while accessibility service continues to receive events or perform actions across other foreground apps
- **MobileEDR:telemetry** — Camera sensor access began from app identity and remained active for sustained capture interval in app context not mapped to approved video recording workflow
- **MobileEDR:telemetry** — Camera sensor access occurred while AppState=background, foreground service active without visible user action, or DeviceLockState=locked during capture interval
- **MobileEDR:telemetry** — Foreground service continues accessing camera, microphone, location, or other while-in-use sensors after service promotion and outside recent user interaction
- **User Interface** — None

## Analytics using this component

- [AN1679 - Analytic 1679](../Analytics/AN1679.md)
- [AN1711 - Analytic 1711](../Analytics/AN1711.md)
- [AN1713 - Analytic 1713](../Analytics/AN1713.md)
- [AN1714 - Analytic 1714](../Analytics/AN1714.md)
- [AN1733 - Analytic 1733](../Analytics/AN1733.md)
- [AN1734 - Analytic 1734](../Analytics/AN1734.md)
- [AN1745 - Analytic 1745](../Analytics/AN1745.md)
- [AN1747 - Analytic 1747](../Analytics/AN1747.md)
- [AN1748 - Analytic 1748](../Analytics/AN1748.md)
- [AN1802 - Analytic 1802](../Analytics/AN1802.md)
- [AN1803 - Analytic 1803](../Analytics/AN1803.md)
- [AN1808 - Analytic 1808](../Analytics/AN1808.md)
- [AN2290 - Analytic 2290](../Analytics/AN2290.md)
