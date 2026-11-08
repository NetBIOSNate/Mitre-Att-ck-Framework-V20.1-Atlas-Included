# T1056.003 - Web Portal Capture

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1056 - Input Capture](../README.md)

Adversaries may install code on externally facing portals, such as a VPN login page, to capture and transmit credentials of users who attempt to log into the service. For example, a compromised login page may log provided user credentials before logging the user in to the service.

This variation on input capture may be conducted post-compromise using legitimate administrative access as a backup measure to maintain network access through [External Remote Services](https://attack.mitre.org/techniques/T1133) and [Valid Accounts](https://attack.mitre.org/techniques/T1078) or as part of the initial compromise by exploitation of the externally facing web service.(Citation: Volexity Virtual Private Keylogging)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1056/003)

**Tactics**  [Credential Access](../../../09%20TA0006%20-%20Credential%20Access/README.md), [Collection](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0029 - Cutting Edge](../../../../Threat%20Intelligence/Campaigns/C0029%20-%20Cutting%20Edge.md) — During [Cutting Edge](https://attack.mitre.org/campaigns/C0029), threat actors modified the JavaScript loaded by the Ivanti Connect Secure login page to capture credentials entered.(Citation: Volexity Ivanti Zero-Day Exploitation January 2024) [Volexity Ivanti Zero-Day Exploitation January 2024](https://www.volexity.com/blog/2024/01/10/active-exploitation-of-two-zero-day-vulnerabilities-in-ivanti-connect-secure-vpn/)
- [S1022 - IceApple](../../../../Threat%20Intelligence/Software/Malware/S1022%20-%20IceApple.md) — The [IceApple](https://attack.mitre.org/software/S1022) OWA credential logger can monitor for OWA authentication requests and log the credentials.(Citation: CrowdStrike IceApple May 2022) [CrowdStrike IceApple May 2022](https://www.crowdstrike.com/wp-content/uploads/2022/05/crowdstrike-iceapple-a-novel-internet-information-services-post-exploitation-framework.pdf)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has collected credentials from a fake Google account login page.(Citation: FBI_KimsukyQR_Jan2026) [FBI_KimsukyQR_Jan2026](https://www.ic3.gov/CSA/2026/260108.pdf)
- [C0030 - Triton Safety Instrumented System Attack](../../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) captured credentials as they were being changed by redirecting text-based login codes to websites they controlled.(Citation: Triton-EENews-2017) [Triton-EENews-2017](https://www.eenews.net/articles/the-inside-story-of-the-worlds-most-dangerous-malware/)
- [S1116 - WARPWIRE](../../../../Threat%20Intelligence/Software/Malware/S1116%20-%20WARPWIRE.md) — [WARPWIRE](https://attack.mitre.org/software/S1116) can capture credentials submitted during the web logon process in order to access layer seven applications such as RDP.(Citation: Mandiant Cutting Edge January 2024) [Mandiant Cutting Edge January 2024](https://www.mandiant.com/resources/blog/suspected-apt-targets-ivanti-zero-day)
- [G1035 - Winter Vivern](../../../../Threat%20Intelligence/Groups/G1035%20-%20Winter%20Vivern.md) — [Winter Vivern](https://attack.mitre.org/groups/G1035) registered and hosted domains to allow for creation of web pages mimicking legitimate government email logon sites to collect logon information.(Citation: SentinelOne WinterVivern 2023) [SentinelOne WinterVivern 2023](https://www.sentinelone.com/labs/winter-vivern-uncovering-a-wave-of-global-espionage/)

## Detection strategies

- [DET0480 - Detection of Credential Harvesting via Web Portal Modification](../../../../Defenses/Detection%20Strategies/DET0480%20-%20Detection%20of%20Credential%20Harvesting%20via%20Web%20Portal%20Modification.md)

## Mitigations

- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow administrator accounts that have permissions to modify the Web content of organization login portals to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.

## Sources

- [Volexity Virtual Private Keylogging](https://www.volexity.com/blog/2015/10/07/virtual-private-keylogging-cisco-web-vpns-leveraged-for-access-and-persistence/)
