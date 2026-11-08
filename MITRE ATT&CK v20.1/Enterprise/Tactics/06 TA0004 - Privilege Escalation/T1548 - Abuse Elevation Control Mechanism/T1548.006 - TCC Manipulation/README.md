# T1548.006 - TCC Manipulation

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1548 - Abuse Elevation Control Mechanism](../README.md)

Adversaries can manipulate or abuse the Transparency, Consent, & Control (TCC) service or database to grant malicious executables elevated permissions. TCC is a Privacy & Security macOS control mechanism used to determine if the running process has permission to access the data or services protected by TCC, such as screen sharing, camera, microphone, or Full Disk Access (FDA).

When an application requests to access data or a service protected by TCC, the TCC daemon (`tccd`) checks the TCC database, located at `/Library/Application Support/com.apple.TCC/TCC.db` (and `~/` equivalent), and an overwrites file (if connected to an MDM) for existing permissions. If permissions do not exist, then the user is prompted to grant permission. Once permissions are granted, the database stores the application's permissions and will not prompt the user again unless reset. For example, when a web browser requests permissions to the user's webcam, once granted the web browser may not explicitly prompt the user again.(Citation: welivesecurity TCC)

Adversaries may access restricted data or services protected by TCC through abusing applications previously granted permissions through [Process Injection](https://attack.mitre.org/techniques/T1055) or executing a malicious binary using another application. For example, adversaries can use Finder, a macOS native app with FDA permissions, to execute a malicious [AppleScript](https://attack.mitre.org/techniques/T1059/002). When executing under the Finder App, the malicious [AppleScript](https://attack.mitre.org/techniques/T1059/002) inherits access to all files on the system without requiring a user prompt. When System Integrity Protection (SIP) is disabled, TCC protections are also disabled. For a system without SIP enabled, adversaries can manipulate the TCC database to add permissions to their malicious executable through loading an adversary controlled TCC database using environment variables and [Launchctl](https://attack.mitre.org/techniques/T1569/001).(Citation: TCC macOS bypass)(Citation: TCC Database)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1548/006)

**Tactics**  [Privilege Escalation](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0534 - TCC Database Manipulation via Launchctl and Unprotected SIP](../../../../Defenses/Detection%20Strategies/DET0534%20-%20TCC%20Database%20Manipulation%20via%20Launchctl%20and%20Unprotected%20SIP.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has used Finder, a macOS native app with FDA permissions, to rename the folder `com.apple.TCC`, then used another process to move the `TCC.db` file to a new location, where SQLite3 was used to edit `TCC.db`. The edited `TCC.db` file allowed code signing authorization, permission access, etc. without requiring a user prompt.(Citation: MIcrosoft Mastra npm Compromise JUN 2026) [MIcrosoft Mastra npm Compromise JUN 2026](https://www.microsoft.com/en-us/security/blog/2026/06/17/postinstall-payload-inside-mastra-npm-supply-chain-compromise/)
- [S0658 - XCSSET](../../../../Threat%20Intelligence/Software/Malware/S0658%20-%20XCSSET.md) — For several modules, [XCSSET](https://attack.mitre.org/software/S0658) attempts to access or list the contents of user folders such as Desktop, Downloads, and Documents. If the folder does not exist or access is denied, it enters a loop where it resets the TCC database and retries access.(Citation: Microsoft March 2025 XCSSET) [Microsoft March 2025 XCSSET](https://www.microsoft.com/en-us/security/blog/2025/03/11/new-xcsset-malware-adds-new-obfuscation-persistence-techniques-to-infect-xcode-projects/)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Routinely check applications using Automation under Security & Privacy System Preferences. To reset permissions, user's can utilize the `tccutil reset` command. When using Mobile Device Management (MDM), review the list of enabled or disabled applications in the `MDMOverrides.plist` which overrides the TCC database.(Citation: TCC macOS bypass) [TCC macOS bypass](https://www.sentinelone.com/labs/bypassing-macos-tcc-user-privacy-protections-by-accident-and-design/)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Remove unnecessary users from the local administrator group on systems.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — When using an MDM, ensure the permissions granted are specific to the requirements of the binary. Full Disk Access should be restricted to only necessary binaries in alignment with policy.

## Sources

- [welivesecurity TCC](https://www.welivesecurity.com/2022/07/19/i-see-what-you-did-there-look-cloudmensis-macos-spyware/)
- [TCC Database](https://web.archive.org/web/20240411112413/https://interpressecurity.com/resources/return-of-the-macos-tcc/)
- [TCC macOS bypass](https://www.sentinelone.com/labs/bypassing-macos-tcc-user-privacy-protections-by-accident-and-design/)
