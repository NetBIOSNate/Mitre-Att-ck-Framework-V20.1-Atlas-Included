# T1098.005 - Device Registration

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1098 - Account Manipulation](../README.md)

Adversaries may register a device to an adversary-controlled account. Devices may be registered in a multifactor authentication (MFA) system, which handles authentication to the network, or in a device management system, which handles device access and compliance.

MFA systems, such as Duo or Okta, allow users to associate devices with their accounts in order to complete MFA requirements. An adversary that compromises a user’s credentials may enroll a new device in order to bypass initial MFA requirements and gain persistent access to a network.(Citation: CISA MFA PrintNightmare)(Citation: DarkReading FireEye SolarWinds) In some cases, the MFA self-enrollment process may require only a username and password to enroll the account's first device or to enroll a device to an inactive account.(Citation: Mandiant APT29 Microsoft 365 2022)

Similarly, an adversary with existing access to a network may register a device or a virtual machine to Entra ID and/or its device management system, Microsoft Intune, in order to access sensitive data or resources while bypassing conditional access policies.(Citation: AADInternals - Device Registration)(Citation: AADInternals - Conditional Access Bypass)(Citation: Microsoft DEV-0537)(Citation: Expel Atlas Lion 2025)

Devices registered in Entra ID may be able to conduct [Internal Spearphishing](https://attack.mitre.org/techniques/T1534) campaigns via intra-organizational emails, which are less likely to be treated as suspicious by the email client.(Citation: Microsoft - Device Registration) Additionally, an adversary may be able to perform a [Service Exhaustion Flood](https://attack.mitre.org/techniques/T1499/002) on an Entra ID tenant by registering a large number of devices.(Citation: AADInternals - BPRT)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1098/005)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md)

## Procedure examples

- [S0677 - AADInternals](../../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can register a device to Azure AD.(Citation: AADInternals Documentation) [AADInternals Documentation](https://o365blog.com/aadinternals)
- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has enrolled their own devices into compromised cloud tenants, including enrolling a device in MFA to an Azure AD environment following a successful password guessing attack against a dormant account.(Citation: Mandiant APT29 Microsoft 365 2022)(Citation: NCSC et al APT29 2024) [Mandiant APT29 Microsoft 365 2022](https://www.mandiant.com/resources/blog/apt29-continues-targeting-microsoft) · [NCSC et al APT29 2024](https://www.ic3.gov/Media/News/2024/240226.pdf)
- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) registered devices for MFA to maintain persistence through victims' VPN.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) registered devices in order to enable mailbox syncing via the `Set-CASMailbox` command.(Citation: Volexity SolarWinds) [Volexity SolarWinds](https://www.volexity.com/blog/2020/12/14/dark-halo-leverages-solarwinds-compromise-to-breach-organizations/)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Require multi-factor authentication to register devices in Entra ID.(Citation: Microsoft - Device Registration) Configure multi-factor authentication systems to disallow enrolling new devices for inactive accounts.(Citation: CISA MFA PrintNightmare) When first enrolling MFA, use conditional access policies to restrict device enrollment to trusted locations or devices, and consider using temporary access passes as an initial MFA solution to enroll a device.(Citation: Mandiant APT29 Microsoft 365 2022) [CISA MFA PrintNightmare](https://www.cisa.gov/uscert/ncas/alerts/aa22-074a) · [Mandiant APT29 Microsoft 365 2022](https://www.mandiant.com/resources/blog/apt29-continues-targeting-microsoft) · [Microsoft - Device Registration](https://www.microsoft.com/security/blog/2022/01/26/evolved-phishing-device-registration-trick-adds-to-phishers-toolbox-for-victims-without-mfa)

## Detection strategies

- [DET0036 - Suspicious Device Registration via Entra ID or MFA Platform](../../../../Defenses/Detection%20Strategies/DET0036%20-%20Suspicious%20Device%20Registration%20via%20Entra%20ID%20or%20MFA%20Platform.md)

## Sources

- [Expel Atlas Lion 2025](https://expel.com/blog/observing-atlas-lion-part-one/)
- [CISA MFA PrintNightmare](https://www.cisa.gov/uscert/ncas/alerts/aa22-074a)
- [Mandiant APT29 Microsoft 365 2022](https://www.mandiant.com/resources/blog/apt29-continues-targeting-microsoft)
- [AADInternals - Conditional Access Bypass](https://o365blog.com/post/mdm)
- [AADInternals - BPRT](https://o365blog.com/post/bprt/)
- [AADInternals - Device Registration](https://o365blog.com/post/devices/)
- [DarkReading FireEye SolarWinds](https://www.darkreading.com/threat-intelligence/fireeye-s-mandia-severity-zero-alert-led-to-discovery-of-solarwinds-attack)
- [Microsoft - Device Registration](https://www.microsoft.com/security/blog/2022/01/26/evolved-phishing-device-registration-trick-adds-to-phishers-toolbox-for-victims-without-mfa)
- [Microsoft DEV-0537](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
