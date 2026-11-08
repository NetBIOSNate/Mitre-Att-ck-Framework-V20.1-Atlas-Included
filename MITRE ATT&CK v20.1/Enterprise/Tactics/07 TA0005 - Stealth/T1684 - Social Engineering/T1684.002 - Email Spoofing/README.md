# T1684.002 - Email Spoofing

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1684 - Social Engineering](../README.md)

Adversaries may fake, or spoof, a sender’s identity by modifying the value of relevant email headers in order to establish contact with victims under false pretenses.(Citation: Proofpoint TA427 April 2024) In addition to actual email content, email headers (such as the FROM header, which contains the email address of the sender) may also be modified. Email clients display these headers when emails appear in a victim's inbox, which may cause modified emails to appear as if they were from the spoofed entity.

Enterprise environments can use Domain-based Message Authentication, Reporting, and Conformance (DMARC) as an email authentication protocol that references results of the Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) configurations. SPF and DKIM are configured separately in DNS: SPF verifies that the sending server is authorized for the domain, while DKIM uses a digital signature to verify email integrity and domain authentication. Together, they validate email authenticity and specify how receiving servers should handle authentication failures. Without enforced identity authentication, adversaries may compromise the integrity of an authentication check with altered headers that would not have otherwise passed.(Citation: Cloudflare DMARC, DKIM, and SPF)(Citation: DMARC-overview)(Citation: Proofpoint-DMARC)

An example of a weak or absent DMARC policy is `v=DMARC1; p=none; fo=1;`. The `p=none` indicates no action should be taken, and therefore no filtering action will take place, even if an email fails authentication checks (i.e., SPF and/or DKIM fail). When a DMARC policy indicates no action, the email will still be delivered to the victim’s inbox.(Citation: ic3-dprk) 

Adversaries have abused weak or absent DMARC policies to circumvent authentication checks and conceal social engineering attempts. Adversaries can alter email headers to include legitimate domain names with fake usernames or impersonate legitimate users via [Impersonation](https://attack.mitre.org/techniques/T1684/001) for [Phishing](https://attack.mitre.org/techniques/T1566). Additionally, adversaries may abuse Microsoft 365’s Direct Send functionality to spoof internal users by using internal devices like printers to send emails without authentication.(Citation: Barnea DirectSend)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1684/002)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0431 - Detection Strategy for Email Spoofing](../../../../Defenses/Detection%20Strategies/DET0431%20-%20Detection%20Strategy%20for%20Email%20Spoofing.md)

## Mitigations

- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Use anti-spoofing and email authentication mechanisms to filter messages based on validity checks of the sender domain (using SPF) and integrity of messages (using DKIM). Enabling these mechanisms within an organization (through policies such as DMARC) may enable recipients (intra-org and cross domain) to perform similar message filtering and validation.(Citation: Microsoft Anti Spoofing)(Citation: ACSC Email Spoofing) [ACSC Email Spoofing](https://web.archive.org/web/20210708014107/https://www.cyber.gov.au/sites/default/files/2019-03/spoof_email_sender_policy_framework.pdf) · [Microsoft Anti Spoofing](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spoofing-protection?view=o365-worldwide)

## Sources

- [Cloudflare DMARC, DKIM, and SPF](https://www.cloudflare.com/learning/email-security/dmarc-dkim-spf/)
- [DMARC-overview](https://dmarc.org/overview)
- [ic3-dprk](https://www.ic3.gov/CSA/2024/240502.pdf)
- [Proofpoint TA427 April 2024](https://www.proofpoint.com/us/blog/threat-insight/social-engineering-dmarc-abuse-ta427s-art-information-gathering)
- [Proofpoint-DMARC](https://www.proofpoint.com/us/threat-reference/dmarc)
- [Barnea DirectSend](https://www.varonis.com/blog/direct-send-exploit)
