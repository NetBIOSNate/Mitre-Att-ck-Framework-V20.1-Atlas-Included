# T1639.001 - Exfiltration Over Unencrypted Non-C2 Protocol

[Mobile](../../../../README.md) / [Exfiltration](../../README.md) / [T1639 - Exfiltration Over Alternative Protocol](../README.md)

Adversaries may steal data by exfiltrating it over an un-encrypted network protocol other than that of the existing command and control channel. The data may also be sent to an alternate network location from the main command and control server.

Adversaries may opt to obfuscate this data, without the use of encryption, within network protocols that are natively unencrypted (such as HTTP, FTP, or DNS). Adversaries may employ custom or publicly available encoding/compression algorithms (such as base64) or embed data within protocol headers and fields.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1639/001)

**Tactics**  [Exfiltration](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S0655 - BusyGasper](../../../../Threat%20Intelligence/Software/Malware/S0655%20-%20BusyGasper.md) — [BusyGasper](https://attack.mitre.org/software/S0655) can download text files with commands from an FTP server and exfiltrate data via email.(Citation: SecureList BusyGasper) [SecureList BusyGasper](https://securelist.com/busygasper-the-unfriendly-spy/87627/)
- [S0425 - Corona Updates](../../../../Threat%20Intelligence/Software/Malware/S0425%20-%20Corona%20Updates.md) — [Corona Updates](https://attack.mitre.org/software/S0425) has exfiltrated data using FTP.(Citation: TrendMicro Coronavirus Updates) [TrendMicro Coronavirus Updates](https://blog.trendmicro.com/trendlabs-security-intelligence/coronavirus-update-app-leads-to-project-spy-android-and-ios-spyware/)
- [S9006 - VajraSpy](../../../../Threat%20Intelligence/Software/Malware/S9006%20-%20VajraSpy.md) — [VajraSpy](https://attack.mitre.org/software/S9006) has used Retrofit, an HTTP client for Android, to upload unencrypted data to the C2 server via HTTP.(Citation: ESET_VajraSpy_Feb2024) [ESET_VajraSpy_Feb2024](https://www.welivesecurity.com/en/eset-research/vajraspy-patchwork-espionage-apps/)

## Detection strategies

- [DET0701 - Detection of Exfiltration Over Unencrypted Non-C2 Protocol](../../../../Defenses/Detection%20Strategies/DET0701%20-%20Detection%20of%20Exfiltration%20Over%20Unencrypted%20Non-C2%20Protocol.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-30.html)
