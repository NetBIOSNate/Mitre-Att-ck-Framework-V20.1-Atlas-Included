# T1552.002 - Credentials in Registry

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1552 - Unsecured Credentials](../README.md)

Adversaries may search the Registry on compromised systems for insecurely stored credentials. The Windows Registry stores configuration information that can be used by the system or other programs. Adversaries may query the Registry looking for credentials and passwords that have been stored for use by other programs or services. Sometimes these credentials are used for automatic logons.

Example commands to find Registry keys related to password information:(Citation: Pentestlab Stored Credentials)

* Local Machine Hive: <code>reg query HKLM /f password /t REG_SZ /s</code>
* Current User Hive: <code>reg query HKCU /f password /t REG_SZ /s</code>

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1552/002)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0331 - Agent Tesla](../../../../Threat%20Intelligence/Software/Malware/S0331%20-%20Agent%20Tesla.md) — [Agent Tesla](https://attack.mitre.org/software/S0331) has the ability to extract credentials from the Registry.(Citation: SentinelLabs Agent Tesla Aug 2020) [SentinelLabs Agent Tesla Aug 2020](https://labs.sentinelone.com/agent-tesla-old-rat-uses-new-tricks-to-stay-on-top/)
- [G0050 - APT32](../../../../Threat%20Intelligence/Groups/G0050%20-%20APT32.md) — [APT32](https://attack.mitre.org/groups/G0050) used Outlook Credential Dumper to harvest credentials stored in Windows registry.(Citation: Cybereason Oceanlotus May 2017)(Citation: Cybereason Cobalt Kitty 2017) [Cybereason Oceanlotus May 2017](https://www.cybereason.com/blog/operation-cobalt-kitty-apt) · [Cybereason Cobalt Kitty 2017](https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf)
- [S1022 - IceApple](../../../../Threat%20Intelligence/Software/Malware/S1022%20-%20IceApple.md) — [IceApple](https://attack.mitre.org/software/S1022) can harvest credentials from local and remote host registries.(Citation: CrowdStrike IceApple May 2022) [CrowdStrike IceApple May 2022](https://www.crowdstrike.com/wp-content/uploads/2022/05/crowdstrike-iceapple-a-novel-internet-information-services-post-exploitation-framework.pdf)
- [S0194 - PowerSploit](../../../../Threat%20Intelligence/Software/Tools/S0194%20-%20PowerSploit.md) — [PowerSploit](https://attack.mitre.org/software/S0194) has several modules that search the Windows Registry for stored credentials: <code>Get-UnattendedInstallFile</code>, <code>Get-Webconfig</code>, <code>Get-ApplicationHost</code>, <code>Get-SiteListPassword</code>, <code>Get-CachedGPPPassword</code>, and <code>Get-RegistryAutoLogon</code>.(Citation: Pentestlab Stored Credentials) [Pentestlab Stored Credentials](https://pentestlab.blog/2017/04/19/stored-credentials/)
- [G1039 - RedCurl](../../../../Threat%20Intelligence/Groups/G1039%20-%20RedCurl.md) — [RedCurl](https://attack.mitre.org/groups/G1039) used [LaZagne](https://attack.mitre.org/software/S0349) to obtain passwords in the Registry.(Citation: group-ib_redcurl1)(Citation: group-ib_redcurl2) [group-ib_redcurl1](https://www.group-ib.com/resources/research-hub/red-curl/) · [group-ib_redcurl2](https://www.group-ib.com/resources/research-hub/red-curl-2/)
- [S0075 - Reg](../../../../Threat%20Intelligence/Software/Tools/S0075%20-%20Reg.md) — [Reg](https://attack.mitre.org/software/S0075) may be used to find credentials in the Windows Registry.(Citation: Pentestlab Stored Credentials) [Pentestlab Stored Credentials](https://pentestlab.blog/2017/04/19/stored-credentials/)
- [S1183 - StrelaStealer](../../../../Threat%20Intelligence/Software/Malware/S1183%20-%20StrelaStealer.md) — [StrelaStealer](https://attack.mitre.org/software/S1183) enumerates the registry key `HKCU\SOFTWARE\Microsoft\Office\16.0\Outlook\Profiles\Outlook\9375CFF0413111d3B88A00104B2A6676\` to identify the values for "IMAP User," "IMAP Server," and "IMAP Password" associated with the Outlook email application.(Citation: DCSO StrelaStealer 2022)(Citation: Fortgale StrelaStealer 2023)(Citation: IBM StrelaStealer 2024) [DCSO StrelaStealer 2022](https://medium.com/@DCSO_CyTec/shortandmalicious-strelastealer-aims-for-mail-credentials-a4c3e78c8abc) · [Fortgale StrelaStealer 2023](https://fortgale.com/blog/malware-analysis/strelastealer-malware-analysis-2/) · [IBM StrelaStealer 2024](https://securityintelligence.com/x-force/strela-stealer-todays-invoice-tomorrows-phish/)
- [S0266 - TrickBot](../../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) has retrieved PuTTY credentials by querying the <code>Software\SimonTatham\Putty\Sessions</code> registry key (Citation: TrendMicro Trickbot Feb 2019) [TrendMicro Trickbot Feb 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/trickbot-adds-remote-application-credential-grabbing-capabilities-to-its-repertoire/)
- [S0476 - Valak](../../../../Threat%20Intelligence/Software/Malware/S0476%20-%20Valak.md) — [Valak](https://attack.mitre.org/software/S0476) can use the clientgrabber module to steal e-mail credentials from the Registry.(Citation: SentinelOne Valak June 2020) [SentinelOne Valak June 2020](https://assets.sentinelone.com/labs/sentinel-one-valak-i)
- [G1055 - VOID MANTICORE](../../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) had exported credentials from registry hives to include those stored in HKLM.(Citation: Check Point VOID MANTICORE Handala Hack March 2026) [Check Point VOID MANTICORE Handala Hack March 2026](https://research.checkpoint.com/2026/handala-hack-unveiling-groups-modus-operandi/)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Proactively search for credentials within the Registry and attempt to remediate the risk.
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Do not store credentials within the Registry.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — If it is necessary that software must store credentials in the Registry, then ensure the associated accounts have limited permissions so they cannot be abused if obtained by an adversary.

## Detection strategies

- [DET0250 - Detect Credential Discovery via Windows Registry Enumeration](../../../../Defenses/Detection%20Strategies/DET0250%20-%20Detect%20Credential%20Discovery%20via%20Windows%20Registry%20Enumeration.md)

## Sources

- [Pentestlab Stored Credentials](https://pentestlab.blog/2017/04/19/stored-credentials/)
