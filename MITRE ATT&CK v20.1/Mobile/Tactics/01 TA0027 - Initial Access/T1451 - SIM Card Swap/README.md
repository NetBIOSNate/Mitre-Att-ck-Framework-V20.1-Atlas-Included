# T1451 - SIM Card Swap

[Mobile](../../../README.md) / [Initial Access](../README.md)

Adversaries may gain access to mobile devices through transfers or swaps from victims’ phone numbers to adversary-controlled SIM cards and mobile devices.(Citation: ATT SIM Swap Scams)(Citation: Verizon SIM Swapping) 

The typical process is as follows:  

1. Adversaries will first gather information about victims through [Phishing](https://attack.mitre.org/techniques/T1660), social engineering, data breaches, or other avenues. 
2. Adversaries will then impersonate victims as they contact mobile carriers to request for the SIM swaps. For example, adversaries would provide victims’ name and address to mobile carriers; once authenticated, adversaries would request for victims’ phone numbers to be transferred to adversary-controlled SIM cards.  
3. Once completed, victims will lose mobile data, such as text messages and phone calls, on their mobile devices. In turn, adversaries will receive mobile data that was intended for the victims.  

Adversaries may use the intercepted SMS messages to log into online accounts that use SMS-based authentication. Specifically, adversaries may use SMS-based authentication to log into banking and/or cryptocurrency accounts, then transfer funds to adversary-controlled wallets.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1451)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [G1004 - LAPSUS$](../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has used SIM swapping to gain access to victims’ mobile devices.(Citation: Krebs LAPUSS Mar2022)(Citation: Microsoft DEV-0537 Mar2022) [Krebs LAPUSS Mar2022](https://krebsonsecurity.com/2022/03/a-closer-look-at-the-lapsus-data-extortion-group/) · [Microsoft DEV-0537 Mar2022](https://www.microsoft.com/en-us/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has used SIM swapping to bypass MFA and to maintain persistence on mobile carrier networks and SIM cards.(Citation: Mphasis SS_SIM_Swap Apr2024)(Citation: Mandiant UNC3944 May 2025)(Citation: CrowdStrike Scattered Spider JUL 2025)(Citation: Check Point Scattered Spider JUL 2025) [CrowdStrike Scattered Spider JUL 2025](https://www.crowdstrike.com/en-us/blog/crowdstrike-services-observes-scattered-spider-escalate-attacks/) · [Check Point Scattered Spider JUL 2025](https://blog.checkpoint.com/research/exposing-scattered-spider-new-indicators-highlight-growing-threat-to-enterprises-and-aviation/) · [Mandiant UNC3944 May 2025](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations) · [Mphasis SS_SIM_Swap Apr2024](https://www.mphasis.com/content/dam/mphasis-com/global/en/home/services/cybersecurity/scattered-spider-conducts-sim-swapping-attacks-12.pdf)

## Mitigations

- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — Enterprises should monitor for SIM card changes on the Enterprise Mobility Management (EMM) or the Mobile Device Management (MDM).
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — The user should become familiar with social engineering tactics that ask for Personally Identifiable Information (PII). Additionally, the user should include the use of hardware tokens, biometrics, and other non-SMS based authentication mechanisms where possible. Finally, the user should enable SIM swapping protections offered by the mobile carrier, such as setting up a PIN or password to authorize any changes to the account.

## Detection strategies

- [DET0658 - Detection of SIM Card Swap](../../../Defenses/Detection%20Strategies/DET0658%20-%20Detection%20of%20SIM%20Card%20Swap.md)

## Sources

- [ATT SIM Swap Scams](https://www.research.att.com/sites/cyberaware/ni/blog/sim_swap.html)
- [Verizon SIM Swapping](https://www.verizon.com/about/account-security/sim-swapping)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/stack-threats/STA-22.html)
