# T1087.003 - Email Account

[Enterprise](../../../../README.md) / [Discovery](../../README.md) / [T1087 - Account Discovery](../README.md)

Adversaries may attempt to get a listing of email addresses and accounts. Adversaries may try to dump Exchange address lists such as global address lists (GALs).(Citation: Microsoft Exchange Address Lists)

In on-premises Exchange and Exchange Online, the <code>Get-GlobalAddressList</code> PowerShell cmdlet can be used to obtain email addresses and accounts from a domain using an authenticated session.(Citation: Microsoft getglobaladdresslist)(Citation: Black Hills Attacking Exchange MailSniper, 2016)

In Google Workspace, the GAL is shared with Microsoft Outlook users through the Google Workspace Sync for Microsoft Outlook (GWSMO) service. Additionally, the Google Workspace Directory allows for users to get a listing of other users within the organization.(Citation: Google Workspace Global Access List)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1087/003)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Office Suite](../../../../Platforms/Office%20Suite.md)

## Procedure examples

- [S0093 - Backdoor.Oldrea](../../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) collects address book information from Outlook.(Citation: Symantec Dragonfly) [Symantec Dragonfly](https://community.broadcom.com/symantecenterprise/communities/community-home/librarydocuments/viewdocument?DocumentKey=7382dce7-0260-4782-84cc-890971ed3f17&CommunityKey=1ecf5f55-9545-44d6-b0f4-4e4a7f5f5e68&tab=librarydocuments)
- [S0635 - BoomBox](../../../../Threat%20Intelligence/Software/Malware/S0635%20-%20BoomBox.md) — [BoomBox](https://attack.mitre.org/software/S0635) can execute an LDAP query to discover e-mail accounts for domain users.(Citation: MSTIC Nobelium Toolset May 2021) [MSTIC Nobelium Toolset May 2021](https://www.microsoft.com/security/blog/2021/05/28/breaking-down-nobeliums-latest-early-stage-toolset/)
- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) accessed Azure AD to identify email addresses.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [S0367 - Emotet](../../../../Threat%20Intelligence/Software/Malware/S0367%20-%20Emotet.md) — [Emotet](https://attack.mitre.org/software/S0367) has been observed leveraging a module that can scrape email addresses from Outlook.(Citation: CIS Emotet Dec 2018)(Citation: IBM IcedID November 2017)(Citation: Binary Defense Emotes Wi-Fi Spreader) [Binary Defense Emotes Wi-Fi Spreader](https://www.binarydefense.com/resources/blog/emotet-evolves-with-new-wi-fi-spreader/) · [CIS Emotet Dec 2018](https://www.cisecurity.org/white-papers/ms-isac-security-primer-emotet/) · [IBM IcedID November 2017](https://securityintelligence.com/new-banking-trojan-icedid-discovered-by-ibm-x-force-research/)
- [S0531 - Grandoreiro](../../../../Threat%20Intelligence/Software/Malware/S0531%20-%20Grandoreiro.md) — [Grandoreiro](https://attack.mitre.org/software/S0531) can parse Outlook .pst files to extract e-mail addresses.(Citation: ESET Grandoreiro April 2020) [ESET Grandoreiro April 2020](https://www.welivesecurity.com/2020/04/28/grandoreiro-how-engorged-can-exe-get/)
- [C0038 - HomeLand Justice](../../../../Threat%20Intelligence/Campaigns/C0038%20-%20HomeLand%20Justice.md) — During [HomeLand Justice](https://attack.mitre.org/campaigns/C0038), threat actors used compromised Exchange accounts to search mailboxes for administrator accounts.(Citation: CISA Iran Albanian Attacks September 2022) [CISA Iran Albanian Attacks September 2022](https://www.cisa.gov/news-events/cybersecurity-advisories/aa22-264a)
- [S9044 - Kali365](../../../../Threat%20Intelligence/Software/Malware/S9044%20-%20Kali365.md) — [Kali365](https://attack.mitre.org/software/S9044) has leveraged an Exchange Admin module that utilizes Graph to enumerate mailboxes in victim environments.(Citation: Huntress Kali365 Device Code June 2026) [Huntress Kali365 Device Code June 2026](https://www.huntress.com/blog/kali365-device-code-phishing-kit)
- [S0681 - Lizar](../../../../Threat%20Intelligence/Software/Malware/S0681%20-%20Lizar.md) — [Lizar](https://attack.mitre.org/software/S0681) can collect email accounts from Microsoft Outlook and Mozilla Thunderbird.(Citation: BiZone Lizar May 2021) [BiZone Lizar May 2021](https://bi-zone.medium.com/from-pentest-to-apt-attack-cybercriminal-group-fin7-disguises-its-malware-as-an-ethical-hackers-c23c9a75e319)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has used Powershell to discover email accounts.(Citation: DFIR Report APT35 ProxyShell March 2022) [DFIR Report APT35 ProxyShell March 2022](https://thedfirreport.com/2022/03/21/apt35-automates-initial-access-using-proxyshell)
- [S0413 - MailSniper](../../../../Threat%20Intelligence/Software/Tools/S0413%20-%20MailSniper.md) — [MailSniper](https://attack.mitre.org/software/S0413) can be used to obtain account names from Exchange and Office 365 using the <code>Get-GlobalAddressList</code> cmdlet.(Citation: Black Hills Attacking Exchange MailSniper, 2016) [Black Hills Attacking Exchange MailSniper, 2016](https://www.blackhillsinfosec.com/attacking-exchange-with-mailsniper/)
- [G1039 - RedCurl](../../../../Threat%20Intelligence/Groups/G1039%20-%20RedCurl.md) — [RedCurl](https://attack.mitre.org/groups/G1039) has collected information about email accounts.(Citation: group-ib_redcurl1)(Citation: group-ib_redcurl2) [group-ib_redcurl1](https://www.group-ib.com/resources/research-hub/red-curl/) · [group-ib_redcurl2](https://www.group-ib.com/resources/research-hub/red-curl-2/)
- [S0358 - Ruler](../../../../Threat%20Intelligence/Software/Tools/S0358%20-%20Ruler.md) — [Ruler](https://attack.mitre.org/software/S0358) can be used to enumerate Exchange users and dump the GAL.(Citation: SensePost Ruler GitHub) [SensePost Ruler GitHub](https://github.com/sensepost/ruler)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) used malware to enumerate email settings, including usernames and passwords, from the M.E.Doc application.(Citation: ESET Telebots July 2017) [ESET Telebots July 2017](https://www.welivesecurity.com/2017/07/04/analysis-of-telebots-cunning-backdoor/)
- [G0092 - TA505](../../../../Threat%20Intelligence/Groups/G0092%20-%20TA505.md) — [TA505](https://attack.mitre.org/groups/G0092) has used the tool EmailStealer to steal and send lists of e-mail addresses to a remote server.(Citation: Trend Micro TA505 June 2019) [Trend Micro TA505 June 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/shifting-tactics-breaking-down-ta505-groups-use-of-html-rats-and-other-techniques-in-latest-campaigns/)
- [S0266 - TrickBot](../../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) collects email addresses from Outlook.(Citation: Trend Micro Trickbot Nov 2018) [Trend Micro Trickbot Nov 2018](https://blog.trendmicro.com/trendlabs-security-intelligence/trickbot-shows-off-new-trick-password-grabber-module/)

## Detection strategies

- [DET0229 - Enumeration of Global Address Lists via Email Account Discovery](../../../../Defenses/Detection%20Strategies/DET0229%20-%20Enumeration%20of%20Global%20Address%20Lists%20via%20Email%20Account%20Discovery.md)

## Sources

- [Black Hills Attacking Exchange MailSniper, 2016](https://www.blackhillsinfosec.com/attacking-exchange-with-mailsniper/)
- [Google Workspace Global Access List](https://support.google.com/a/answer/166870?hl=en)
- [Microsoft Exchange Address Lists](https://docs.microsoft.com/en-us/exchange/email-addresses-and-address-books/address-lists/address-lists?view=exchserver-2019)
- [Microsoft getglobaladdresslist](https://docs.microsoft.com/en-us/powershell/module/exchange/email-addresses-and-address-books/get-globaladdresslist)
