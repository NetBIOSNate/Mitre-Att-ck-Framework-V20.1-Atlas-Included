# T1556.006 - Multi-Factor Authentication

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1556 - Modify Authentication Process](../README.md)

Adversaries may disable or modify multi-factor authentication (MFA) mechanisms to enable persistent access to compromised accounts.

Once adversaries have gained access to a network by either compromising an account lacking MFA or by employing an MFA bypass method such as [Multi-Factor Authentication Request Generation](https://attack.mitre.org/techniques/T1621), adversaries may leverage their access to modify or completely disable MFA defenses. This can be accomplished by abusing legitimate features, such as excluding users from Azure AD Conditional Access Policies, registering a new yet vulnerable/adversary-controlled MFA method, or by manually patching MFA programs and configuration files to bypass expected functionality.(Citation: Mandiant APT42)(Citation: Azure AD Conditional Access Exclusions)

For example, modifying the Windows hosts file (`C:\windows\system32\drivers\etc\hosts`) to redirect MFA calls to localhost instead of an MFA server may cause the MFA process to fail. If a "fail open" policy is in place, any otherwise successful authentication attempt may be granted access without enforcing MFA.(Citation: Russians Exploit Default MFA Protocol - CISA March 2022) 

Depending on the scope, goals, and privileges of the adversary, MFA defenses may be disabled for individual accounts or for all accounts tied to a larger group, such as all domain accounts in a victim's network environment.(Citation: Russians Exploit Default MFA Protocol - CISA March 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1556/006)

**Tactics**  [Persistence](../../README.md), [Defense Impairment](../../../08%20TA0112%20-%20Defense%20Impairment/README.md), [Credential Access](../../../09%20TA0006%20-%20Credential%20Access/README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0190 - Detect MFA Modification or Disabling Across Platforms](../../../../Defenses/Detection%20Strategies/DET0190%20-%20Detect%20MFA%20Modification%20or%20Disabling%20Across%20Platforms.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Review MFA actions alongside authentication logs to ensure that MFA-based logins are functioning as intended. Review user accounts to ensure that all accounts have MFA enabled.(Citation: Mandiant Cloudy Logs 2023) [Mandiant Cloudy Logs 2023](https://www.mandiant.com/resources/blog/cloud-bad-log-configurations)
- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Ensure that MFA and MFA policies and requirements are properly implemented for existing and deactivated or dormant accounts and devices. If possible, consider configuring MFA solutions to "fail closed" rather than grant access in case of serious errors.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure that proper policies are implemented to dictate the secure enrollment and deactivation of MFA for user accounts.

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries modified two-factor settings within the FortiGate solution to `unset`.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S0677 - AADInternals](../../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — The [AADInternals](https://attack.mitre.org/software/S0677) `Set-AADIntUserMFA` command can be used to disable MFA for a specified user.
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — After compromising user accounts, [Scattered Spider](https://attack.mitre.org/groups/G1015) registers their own MFA tokens.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [S1104 - SLOWPULSE](../../../../Threat%20Intelligence/Software/Malware/S1104%20-%20SLOWPULSE.md) — [SLOWPULSE](https://attack.mitre.org/software/S1104) can insert malicious logic to bypass RADIUS and ACE two factor authentication (2FA) flows if a designated attacker-supplied password is provided.(Citation: Mandiant Pulse Secure Zero-Day April 2021) [Mandiant Pulse Secure Zero-Day April 2021](https://www.mandiant.com/resources/blog/suspected-apt-actors-leverage-bypass-techniques-pulse-secure-zero-day)

## Sources

- [Russians Exploit Default MFA Protocol - CISA March 2022](https://www.cisa.gov/uscert/ncas/alerts/aa22-074a)
- [Mandiant APT42](https://www.mandiant.com/media/17826)
- [Azure AD Conditional Access Exclusions](https://docs.microsoft.com/en-us/azure/active-directory/governance/conditional-access-exclusion)
