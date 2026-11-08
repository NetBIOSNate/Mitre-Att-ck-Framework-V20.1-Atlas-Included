# T0817 - Drive-by Compromise

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may gain access to a system during a drive-by compromise, when a user visits a website as part of a regular browsing session. With this technique, the user's web browser is targeted and exploited simply by visiting the compromised website. 

The adversary may target a specific community, such as trusted third party suppliers or other industry specific groups, which often visit the target website. This kind of targeted attack relies on a common interest, and is known as a strategic web compromise or watering hole attack. 

The National Cyber Awareness System (NCAS) has issued a Technical Alert (TA) regarding Russian government cyber activity targeting critical infrastructure sectors. (Citation: Cybersecurity & Infrastructure Security Agency March 2018) Analysis by DHS and FBI has noted two distinct categories of victims in the Dragonfly campaign on the Western energy sector: staging and intended targets. The adversary targeted the less secure networks of staging targets, including trusted third-party suppliers and related peripheral organizations. Initial access to the intended targets used watering hole attacks to target process control, ICS, and critical infrastructure related trade publications and informational websites.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0817)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Procedure examples

- [G1000 - ALLANITE](../../../Threat%20Intelligence/Groups/G1000%20-%20ALLANITE.md) — [ALLANITE](https://attack.mitre.org/groups/G1000) leverages watering hole attacks to gain access into electric utilities. (Citation: Eduard Kovacs May 2018) [Eduard Kovacs May 2018](https://web.archive.org/web/20220120001230/https://www.cyberviser.com/2018/05/group-linked-to-shamoon-attacks-targeting-ics-networks-in-middle-east-and-uk/)
- [S0606 - Bad Rabbit](../../../Threat%20Intelligence/Software/Malware/S0606%20-%20Bad%20Rabbit.md) — [Bad Rabbit](https://attack.mitre.org/software/S0606) ransomware spreads through drive-by attacks where insecure websites are compromised. While the target is visiting a legitimate website, a malware dropper is being downloaded from the threat actors infrastructure. (Citation: Orkhan Mamedov, Fedor Sinitsyn, Anton Ivanov October 2017) [Orkhan Mamedov, Fedor Sinitsyn, Anton Ivanov October 2017](https://securelist.com/bad-rabbit-ransomware/82851/)
- [G0035 - Dragonfly](../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) utilized watering hole attacks on energy sector websites by injecting a redirect iframe to deliver [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) or [Trojan.Karagany](https://attack.mitre.org/software/S0094). (Citation: Symantec Security Response July 2014) [Symantec Security Response July 2014](https://docs.broadcom.com/doc/dragonfly_threat_against_western_energy_suppliers#:~:text=The%20attackers%2C%20known%20to%20Symantec,supply%20in%20the%20affected%20countries.)
- [G0049 - OilRig](../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has been seen utilizing watering hole attacks to collect credentials which could be used to gain access into ICS networks. (Citation: Eduard Kovacs May 2018) [Eduard Kovacs May 2018](https://web.archive.org/web/20220120001230/https://www.cyberviser.com/2018/05/group-linked-to-shamoon-attacks-targeting-ics-networks-in-middle-east-and-uk/)
- [G0088 - TEMP.Veles](../../../Threat%20Intelligence/Groups/G0088%20-%20TEMP.Veles.md) — [TEMP.Veles](https://attack.mitre.org/groups/G0088) utilizes watering hole websites to target industrial employees. (Citation: Chris Bing May 2018) [Chris Bing May 2018](https://www.cyberscoop.com/xenotime-ics-cyber-attacks-trisis-dragos/)

## Mitigations

- [M0948 - Application Isolation and Sandboxing](../../../Defenses/Mitigations/M0948%20-%20Application%20Isolation%20and%20Sandboxing.md) — Built-in browser sandboxes and application isolation may be used to contain web-based malware.
- [M0950 - Exploit Protection](../../../Defenses/Mitigations/M0950%20-%20Exploit%20Protection.md) — Utilize exploit protection to prevent activities which may be exploited through malicious web sites.
- [M0921 - Restrict Web-Based Content](../../../Defenses/Mitigations/M0921%20-%20Restrict%20Web-Based%20Content.md) — Restrict browsers to limit the capabilities of malicious ads and Javascript.
- [M0951 - Update Software](../../../Defenses/Mitigations/M0951%20-%20Update%20Software.md) — Ensure all browsers and plugins are kept updated to help prevent the exploit phase of this technique. Use modern browsers with security features enabled.

## Detection strategies

- [DET0782 - Detection of Drive-by Compromise](../../../Defenses/Detection%20Strategies/DET0782%20-%20Detection%20of%20Drive-by%20Compromise.md)

## Targeted assets

- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Sources

- [Cybersecurity & Infrastructure Security Agency March 2018](https://us-cert.cisa.gov/ncas/alerts/TA18-074A)
