# DC0119 - Application Assets

[Mobile](../../README.md) / [Data Components](README.md)

Application Assets represent static or packaged resources bundled with an application that may contain executable logic, configuration data, or hidden payloads.

These assets may include embedded binaries, scripts, configuration files, libraries, or other resources stored within the application package. Adversaries may hide malicious components within application assets to evade detection during installation or initial inspection.

Examples

Android:

- Embedded .dex files loaded dynamically
- Hidden native libraries in APK assets
- Dropped payloads stored within the app sandbox

iOS:

- Embedded frameworks
- Configuration files within the application bundle
- Hidden scripts or secondary binaries packaged with the app

Collection Methods
- Mobile EDR application inspection
- Static application analysis
- Application package scanning during install or sideload events

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0119)

## Log sources and channels

- **Application Vetting** — None
- **iOS:unifiedlog** — Application gaining or using unexpected background execution entitlements or modes
