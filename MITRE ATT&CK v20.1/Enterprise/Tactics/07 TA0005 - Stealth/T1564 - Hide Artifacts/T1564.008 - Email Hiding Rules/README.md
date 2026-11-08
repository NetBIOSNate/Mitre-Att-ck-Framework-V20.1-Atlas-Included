# T1564.008 - Email Hiding Rules

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1564 - Hide Artifacts](../README.md)

Adversaries may use email rules to hide inbound emails in a compromised user's mailbox. Many email clients allow users to create inbox rules for various email functions, including moving emails to other folders, marking emails as read, or deleting emails. Rules may be created or modified within email clients or through external features such as the <code>New-InboxRule</code> or <code>Set-InboxRule</code> [PowerShell](https://attack.mitre.org/techniques/T1059/001) cmdlets on Windows systems.(Citation: Microsoft Inbox Rules)(Citation: MacOS Email Rules)(Citation: Microsoft New-InboxRule)(Citation: Microsoft Set-InboxRule)

Adversaries may utilize email rules within a compromised user's mailbox to delete and/or move emails to less noticeable folders. Adversaries may do this to hide security alerts, C2 communication, or responses to [Internal Spearphishing](https://attack.mitre.org/techniques/T1534) emails sent from the compromised account.

Any user or administrator within the organization (or adversary with valid credentials) may be able to create rules to automatically move or delete emails. These rules can be abused to impair/delay detection had the email content been immediately seen by a user or defender. Malicious rules commonly filter out emails based on key words (such as <code>malware</code>, <code>suspicious</code>, <code>phish</code>, and <code>hack</code>) found in message bodies and subject lines.(Citation: Microsoft Cloud App Security)

In some environments, administrators may be able to enable email rules that operate organization-wide rather than on individual inboxes. For example, Microsoft Exchange supports transport rules that evaluate all mail an organization receives against user-specified conditions, then performs a user-specified action on mail that adheres to those conditions.(Citation: Microsoft Mail Flow Rules 2023) Adversaries that abuse such features may be able to automatically modify or delete all emails related to specific topics (such as internal security incident notifications).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564/008)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Office Suite](../../../../Platforms/Office%20Suite.md)

## Procedure examples

- [G0085 - FIN4](../../../../Threat%20Intelligence/Groups/G0085%20-%20FIN4.md) — [FIN4](https://attack.mitre.org/groups/G0085) has created rules in victims' Microsoft Outlook accounts to automatically delete emails containing words such as “hacked," "phish," and “malware" in a likely attempt to prevent organizations from communicating about their activities.(Citation: FireEye Hacking FIN4 Dec 2014) [FireEye Hacking FIN4 Dec 2014](https://web.archive.org/web/20220313062515/https://www.mandiant.com/sites/default/files/2021-09/rpt-fin4.pdf)
- [S9044 - Kali365](../../../../Threat%20Intelligence/Software/Malware/S9044%20-%20Kali365.md) — [Kali365](https://attack.mitre.org/software/S9044) has the ability to modify email rules to delete email based notifications prior to the victim seeing them.(Citation: SpyCloud Kali365 June 2026) [SpyCloud Kali365 June 2026](https://spycloud.com/blog/kali365-anatomy-of-a-microsoft365-phishing-as-a-service-kit/)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) creates inbound rules on the compromised email accounts of security personnel to automatically delete emails from vendor security products.(Citation: MSTIC Octo Tempest Operations October 2023) [MSTIC Octo Tempest Operations October 2023](https://www.microsoft.com/en-us/security/blog/2023/10/25/octo-tempest-crosses-boundaries-to-facilitate-extortion-encryption-and-destruction/)

## Detection strategies

- [DET0192 - Detection Strategy for Email Hiding Rules](../../../../Defenses/Detection%20Strategies/DET0192%20-%20Detection%20Strategy%20for%20Email%20Hiding%20Rules.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Enterprise email solutions may have monitoring mechanisms that may include the ability to audit inbox rules on a regular basis. In an Exchange environment, Administrators can use `Get-InboxRule` / `Remove-InboxRule` and `Get-TransportRule` / `Remove-TransportRule` to discover and remove potentially malicious inbox and transport rules.(Citation: Microsoft Get-InboxRule)(Citation: Microsoft Manage Mail Flow Rules 2023) [Microsoft Manage Mail Flow Rules 2023](https://learn.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) · [Microsoft Get-InboxRule](https://docs.microsoft.com/en-us/powershell/module/exchange/get-inboxrule?view=exchange-ps)

## Sources

- [MacOS Email Rules](https://support.apple.com/guide/mail/use-rules-to-manage-emails-you-receive-mlhlp1017/mac)
- [Microsoft Mail Flow Rules 2023](https://learn.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
- [Microsoft Inbox Rules](https://support.microsoft.com/en-us/office/manage-email-messages-by-using-rules-c24f5dea-9465-4df4-ad17-a50704d66c59)
- [Microsoft New-InboxRule](https://docs.microsoft.com/en-us/powershell/module/exchange/new-inboxrule?view=exchange-ps)
- [Microsoft Set-InboxRule](https://docs.microsoft.com/en-us/powershell/module/exchange/set-inboxrule?view=exchange-ps)
- [Microsoft Cloud App Security](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/rule-your-inbox-with-microsoft-cloud-app-security/ba-p/299154)
