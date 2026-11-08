# T1665 - Hide Infrastructure

[Enterprise](../../../README.md) / [Command and Control](../README.md)

Adversaries may manipulate network traffic in order to hide and evade detection of their C2 infrastructure. This can be accomplished by identifying and filtering traffic from defensive tools,(Citation: TA571) masking malicious domains to obfuscate the true destination from both automated scanning tools and security researchers,(Citation: Schema-abuse)(Citation: Facad1ng)(Citation: Browser-updates) and otherwise hiding malicious artifacts to delay discovery and prolong the effectiveness of adversary infrastructure that could otherwise be identified, blocked, or taken down entirely.

C2 networks may include the use of [Proxy](https://attack.mitre.org/techniques/T1090) or VPNs to disguise IP addresses, which can allow adversaries to blend in with normal network traffic and bypass conditional access policies or anti-abuse protections. For example, an adversary may use a virtual private cloud to spoof their IP address to closer align with a victim's IP address ranges. This may also bypass security measures relying on geolocation of the source IP address.(Citation: sysdig)(Citation: Orange Residential Proxies)

Adversaries may also attempt to filter network traffic in order to evade defensive tools in numerous ways, including blocking/redirecting common incident responder or security appliance user agents.(Citation: mod_rewrite)(Citation: SocGholish-update) Filtering traffic based on IP and geo-fencing may also avoid automated sandboxing or researcher activity (i.e., [Virtualization/Sandbox Evasion](https://attack.mitre.org/techniques/T1497)).(Citation: TA571)(Citation: mod_rewrite)

Hiding C2 infrastructure may also be supported by [Resource Development](https://attack.mitre.org/tactics/TA0042) activities such as [Acquire Infrastructure](https://attack.mitre.org/techniques/T1583) and [Compromise Infrastructure](https://attack.mitre.org/techniques/T1584). For example, using widely trusted hosting services or domains such as prominent URL shortening providers or marketing services for C2 networks may enable adversaries to present benign content that later redirects victims to malicious web pages or infrastructure once specific conditions are met.(Citation: StarBlizzard)(Citation: QR-cofense)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1665)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [G0016 - APT29](../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) uses compromised residential endpoints, typically within the same ISP IP address range, as proxies to hide the true source of C2 traffic.(Citation: NCSC et al APT29 2024) [NCSC et al APT29 2024](https://www.ic3.gov/Media/News/2024/240226.pdf)
- [S1111 - DarkGate](../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) command and control includes hard-coded domains in the malware masquerading as legitimate services such as Akamai CDN or Amazon Web Services.(Citation: Trellix Darkgate 2023) [Trellix Darkgate 2023](https://www.trellix.com/blogs/research/the-continued-evolution-of-the-darkgate-malware-as-a-service/)
- [S1206 - JumbledPath](../../../Threat%20Intelligence/Software/Malware/S1206%20-%20JumbledPath.md) — [JumbledPath](https://attack.mitre.org/software/S1206) can use a chain of jump hosts to communicate with compromised devices to obscure actor infrastructure.(Citation: Cisco Salt Typhoon FEB 2025) [Cisco Salt Typhoon FEB 2025](https://blog.talosintelligence.com/salt-typhoon-analysis/)
- [C0061 - Operation Digital Eye](../../../Threat%20Intelligence/Campaigns/C0061%20-%20Operation%20Digital%20Eye.md) — During [Operation Digital Eye](https://attack.mitre.org/campaigns/C0061), threat actors used public Cloud infrastructure to mask malicious activity.(Citation: sentinelone operationDigitalEye Dec 2024) [sentinelone operationDigitalEye Dec 2024](https://www.sentinelone.com/labs/operation-digital-eye-chinese-apt-compromises-critical-digital-infrastructure-via-visual-studio-code-tunnels/)
- [C0055 - Quad7 Activity](../../../Threat%20Intelligence/Campaigns/C0055%20-%20Quad7%20Activity.md) — [Quad7 Activity](https://attack.mitre.org/campaigns/C0055) has rotated the compromised SOHO IPs used in password spraying activity to hamper detection and network blocking activities by defenders.(Citation: Microsoft Storm-0940) [Microsoft Storm-0940](https://www.microsoft.com/en-us/security/blog/2024/10/31/chinese-threat-actor-storm-0940-uses-credentials-from-password-spray-attacks-from-a-covert-network/)
- [C0024 - SolarWinds Compromise](../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) set the hostnames of their C2 infrastructure to match legitimate hostnames in the victim environment. They also used IP addresses originating from the same country as the victim for their VPN infrastructure.(Citation: FireEye SUNBURST Backdoor December 2020) [FireEye SUNBURST Backdoor December 2020](https://www.fireeye.com/blog/threat-research/2020/12/evasive-attacker-leverages-solarwinds-supply-chain-compromises-with-sunburst-backdoor.html)
- [S1164 - UPSTYLE](../../../Threat%20Intelligence/Software/Malware/S1164%20-%20UPSTYLE.md) — [UPSTYLE](https://attack.mitre.org/software/S1164) attempts to retrieve a non-existent webpage from the command and control server resulting in hidden commands sent via resulting error messages.(Citation: Volexity UPSTYLE 2024) [Volexity UPSTYLE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)
- [G0128 - ZIRCONIUM](../../../Threat%20Intelligence/Groups/G0128%20-%20ZIRCONIUM.md) — [ZIRCONIUM](https://attack.mitre.org/groups/G0128) has utilized an ORB (operational relay box) network – consisting compromised devices such as small office and home office (SOHO) routers, IoT devices, and leased virtual private servers (VPS) – to obfuscate the origin of C2 traffic.(Citation: ORB Mandiant) [ORB Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-orb-networks)

## Detection strategies

- [DET0411 - Detection Strategy for Hide Infrastructure](../../../Defenses/Detection%20Strategies/DET0411%20-%20Detection%20Strategy%20for%20Hide%20Infrastructure.md)

## Sources

- [SocGholish-update](https://www.proofpoint.com/us/blog/threat-insight/part-1-socgholish-very-real-threat-very-fake-update)
- [TA571](https://www.proofpoint.com/us/blog/threat-insight/security-brief-ta571-delivers-icedid-forked-loader)
- [mod_rewrite](https://bluescreenofjeff.com/2016-04-12-combatting-incident-responders-with-apache-mod_rewrite/)
- [Browser-updates](https://www.proofpoint.com/us/blog/threat-insight/are-you-sure-your-browser-date-current-landscape-fake-browser-updates)
- [StarBlizzard](https://www.microsoft.com/en-us/security/blog/2023/12/07/star-blizzard-increases-sophistication-and-evasion-in-ongoing-attacks/)
- [QR-cofense](https://cofense.com/blog/major-energy-company-targeted-in-large-qr-code-campaign/)
- [Schema-abuse](https://www.mandiant.com/resources/blog/url-obfuscation-schema-abuse)
- [Orange Residential Proxies](https://www.orangecyberdefense.com/global/blog/research/residential-proxies)
- [Facad1ng](https://github.com/spyboy-productions/Facad1ng)
- [sysdig](https://sysdig.com/content/c/pf-2023-global-cloud-threat-report?x=u_WFRi&xs=524303#page=1)
