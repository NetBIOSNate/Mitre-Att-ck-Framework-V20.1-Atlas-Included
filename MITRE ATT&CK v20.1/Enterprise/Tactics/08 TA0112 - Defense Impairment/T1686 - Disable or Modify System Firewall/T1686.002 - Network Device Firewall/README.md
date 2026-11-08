# T1686.002 - Network Device Firewall

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1686 - Disable or Modify System Firewall](../README.md)

Adversaries may disable network device-based firewall mechanisms entirely or add, delete, or modify particular rules in order to bypass controls limiting network usage.  

Adversaries may obtain access to devices such as routers, switches, or other perimeter/network devices and change access control lists (ACLs), security zones, or policy rules to permit otherwise blocked traffic. For example, adversaries may add new network firewall rules to allow access to all internal network subnets without restrictions. Allowing access to internal network subsets may enable unrestricted inbound/outbound connectivity or open paths for command and control and lateral movement.

Adversaries may obtain access to network device management interfaces via [Valid Accounts](https://attack.mitre.org/techniques/T1078) or by exploiting vulnerabilities. In some cases, threat actors may target firewalls and other network infrastructure that are exposed to the internet by leveraging weaknesses in public-facing applications ([Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190)).(Citation: CVE-2024-55591 Detail)

Adversaries may also modify host networking configurations that indirectly manipulate system firewalls, such as adjusting interface bandwidth or network connection request thresholds.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1686/002)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries modified security settings within the victims Fortigate device, utilizing the native CLI. During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries also disabled network traffic logging.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) have created firewall exemptions on specific ports, including ports 443, 6443, 8443, and 9443. (Citation: CISA AA20-239A BeagleBoyz August 2020) [CISA AA20-239A BeagleBoyz August 2020](https://us-cert.cisa.gov/ncas/alerts/aa20-239a)
- [S0687 - Cyclops Blink](../../../../Threat%20Intelligence/Software/Malware/S0687%20-%20Cyclops%20Blink.md) — [Cyclops Blink](https://attack.mitre.org/software/S0687) can modify the Linux iptables firewall to enable C2 communication on network devices via a stored list of port numbers.(Citation: NCSC Cyclops Blink February 2022)(Citation: Trend Micro Cyclops Blink March 2022) [Trend Micro Cyclops Blink March 2022](https://www.trendmicro.com/en_us/research/22/c/cyclops-blink-sets-sights-on-asus-routers--.html) · [NCSC Cyclops Blink February 2022](https://www.ncsc.gov.uk/files/Cyclops-Blink-Malware-Analysis-Report.pdf)
- [S0531 - Grandoreiro](../../../../Threat%20Intelligence/Software/Malware/S0531%20-%20Grandoreiro.md) — [Grandoreiro](https://attack.mitre.org/software/S0531) can block the Deibold Warsaw GAS Tecnologia security tool at the firewall level. (Citation: ESET Grandoreiro April 2020) [ESET Grandoreiro April 2020](https://www.welivesecurity.com/2020/04/28/grandoreiro-how-engorged-can-exe-get/)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has modified the network firewalls access control lists to add IP addresses to bypass security policies and maintain access.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Routinely check account role permissions to ensure only expected users and roles have permission to modify system firewalls.
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Ensure the network firewall is up to date with security patches.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure proper user permissions are in place to prevent adversaries from disabling or modifying firewall settings.

## Detection strategies

- [DET0306 - Detection of Unauthorized Network Firewall Rule Modification](../../../../Defenses/Detection%20Strategies/DET0306%20-%20Detection%20of%20Unauthorized%20Network%20Firewall%20Rule%20Modification.md)

## Sources

- [CVE-2024-55591 Detail](https://nvd.nist.gov/vuln/detail/CVE-2024-55591)
