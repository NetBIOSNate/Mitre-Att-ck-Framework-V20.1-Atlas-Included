# T1667 - Email Bombing

[Enterprise](../../../README.md) / [Impact](../README.md)

Adversaries may flood targeted email addresses with an overwhelming volume of messages. This may bury legitimate emails in a flood of spam and disrupt business operations.(Citation: sophos-bombing)(Citation: krebs-email-bombing)

An adversary may accomplish email bombing by leveraging an automated bot to register a targeted address for e-mail lists that do not validate new signups, such as online newsletters. The result can be a wave of thousands of e-mails that effectively overloads the victim’s inbox.(Citation: krebs-email-bombing)(Citation: hhs-email-bombing)

By sending hundreds or thousands of e-mails in quick succession, adversaries may successfully divert attention away from and bury legitimate messages including security alerts, daily business processes like help desk tickets and client correspondence, or ongoing scams.(Citation: hhs-email-bombing) This behavior can also be used as a tool of harassment.(Citation: krebs-email-bombing)

This behavior may be a precursor for [Spearphishing Voice](https://attack.mitre.org/techniques/T1566/004). For example, an adversary may email bomb a target and then follow up with a phone call to fraudulently offer assistance. This social engineering may lead to the use of [Remote Access Software](https://attack.mitre.org/techniques/T1663) to steal credentials, deploy ransomware, conduct [Financial Theft](https://attack.mitre.org/techniques/T1657)(Citation: sophos-bombing), or engage in other malicious activity.(Citation: rapid7-email-bombing)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1667)

**Tactics**  [Impact](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [Office Suite](../../../Platforms/Office%20Suite.md), [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md)

## Procedure examples

- [G1046 - Storm-1811](../../../Threat%20Intelligence/Groups/G1046%20-%20Storm-1811.md) — [Storm-1811](https://attack.mitre.org/groups/G1046) has deployed large volumes of non-malicious email spam to victims in order to prompt follow-on interactions with the threat actor posing as IT support or helpdesk to resolve the problem.(Citation: rapid7-email-bombing)(Citation: RedCanary Storm-1811 2024) [RedCanary Storm-1811 2024](https://redcanary.com/blog/threat-intelligence/storm-1811-black-basta/) · [rapid7-email-bombing](https://www.rapid7.com/blog/post/2024/05/10/ongoing-social-engineering-campaign-linked-to-black-basta-ransomware-operators)

## Mitigations

- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Use anti-spoofing and email authentication mechanisms to filter messages based on validity checks of the sender domain (using SPF) and integrity of messages (using DKIM). Enabling these mechanisms within an organization (through policies such as DMARC) may enable recipients (intra-org and cross domain) to perform similar message filtering and validation.(Citation: Microsoft Anti Spoofing)(Citation: ACSC Email Spoofing) Note that additional filtering may be necessary if emails are coming from legitimate sources. [ACSC Email Spoofing](https://web.archive.org/web/20210708014107/https://www.cyber.gov.au/sites/default/files/2019-03/spoof_email_sender_policy_framework.pdf) · [Microsoft Anti Spoofing](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spoofing-protection?view=o365-worldwide)
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to be aware of access or manipulation attempts by an adversary to reduce the risk of successful social engineering via e-mail bombing.

## Detection strategies

- [DET0355 - Detection Strategy for Email Bombing](../../../Defenses/Detection%20Strategies/DET0355%20-%20Detection%20Strategy%20for%20Email%20Bombing.md)

## Sources

- [krebs-email-bombing](https://krebsonsecurity.com/2016/08/massive-email-bombs-target-gov-addresses/)
- [sophos-bombing](https://news.sophos.com/en-us/2025/01/21/sophos-mdr-tracks-two-ransomware-campaigns-using-email-bombing-microsoft-teams-vishing/)
- [rapid7-email-bombing](https://www.rapid7.com/blog/post/2024/05/10/ongoing-social-engineering-campaign-linked-to-black-basta-ransomware-operators)
- [hhs-email-bombing](https://www.hhs.gov/sites/default/files/email-bombing-sector-alert-tlpclear.pdf)
