# T1608.004 - Drive-by Target

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1608 - Stage Capabilities](../README.md)

Adversaries may prepare an operational environment to infect systems that visit a website over the normal course of browsing. Endpoint systems may be compromised through browsing to adversary controlled sites, as in [Drive-by Compromise](https://attack.mitre.org/techniques/T1189). In such cases, the user's web browser is typically targeted for exploitation (often not requiring any extra user interaction once landing on the site), but adversaries may also set up websites for non-exploitation behavior such as [Application Access Token](https://attack.mitre.org/techniques/T1550/001). Prior to [Drive-by Compromise](https://attack.mitre.org/techniques/T1189), adversaries must stage resources needed to deliver that exploit to users who browse to an adversary controlled site. Drive-by content can be staged on adversary controlled infrastructure that has been acquired ([Acquire Infrastructure](https://attack.mitre.org/techniques/T1583)) or previously compromised ([Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)).

Adversaries may upload or inject malicious web content, such as [JavaScript](https://attack.mitre.org/techniques/T1059/007), into websites.(Citation: FireEye CFR Watering Hole 2012)(Citation: Gallagher 2015) This may be done in a number of ways, including:

* Inserting malicious scripts into web pages or other user controllable web content such as forum posts
* Modifying script files served to websites from publicly writeable cloud storage buckets
* Crafting malicious web advertisements and purchasing ad space on a website through legitimate ad providers (i.e., [Malvertising](https://attack.mitre.org/techniques/T1583/008))

In addition to staging content to exploit a user's web browser, adversaries may also stage scripting content to profile the user's browser (as in [Gather Victim Host Information](https://attack.mitre.org/techniques/T1592)) to ensure it is vulnerable prior to attempting exploitation.(Citation: ATT ScanBox)

Websites compromised by an adversary and used to stage a drive-by may be ones visited by a specific community, such as government, a particular industry, or region, where the goal is to compromise a specific user or set of users based on a shared interest. This kind of targeted campaign is referred to a strategic web compromise or watering hole attack.

Adversaries may purchase domains similar to legitimate domains (ex: homoglyphs, typosquatting, different top-level domain, etc.) during acquisition of infrastructure ([Domains](https://attack.mitre.org/techniques/T1583/001)) to help facilitate [Drive-by Compromise](https://attack.mitre.org/techniques/T1189).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1608/004)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G0050 - APT32](../../../../Threat%20Intelligence/Groups/G0050%20-%20APT32.md) — [APT32](https://attack.mitre.org/groups/G0050) has stood up websites containing numerous articles and content scraped from the Internet to make them appear legitimate, but some of these pages include malicious JavaScript to profile the potential victim or infect them via a fake software update.(Citation: Volexity Ocean Lotus November 2020) [Volexity Ocean Lotus November 2020](https://www.volexity.com/blog/2020/11/06/oceanlotus-extending-cyber-espionage-operations-through-fake-websites/)
- [C0010 - C0010](../../../../Threat%20Intelligence/Campaigns/C0010%20-%20C0010.md) — For [C0010](https://attack.mitre.org/campaigns/C0010), the threat actors compromised the login page of a legitimate Israeli shipping company and likely established a watering hole that collected visitor information.(Citation: Mandiant UNC3890 Aug 2022) [Mandiant UNC3890 Aug 2022](https://www.mandiant.com/resources/blog/suspected-iranian-actor-targeting-israeli-shipping)
- [G1012 - CURIUM](../../../../Threat%20Intelligence/Groups/G1012%20-%20CURIUM.md) — [CURIUM](https://attack.mitre.org/groups/G1012) used strategic website compromise to fingerprint then target victims.(Citation: PWC Yellow Liderc 2023) [PWC Yellow Liderc 2023](https://www.pwc.com/gx/en/issues/cybersecurity/cyber-threat-intelligence/yellow-liderc-ships-its-scripts-delivers-imaploader-malware.html)
- [G0035 - Dragonfly](../../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) has compromised websites to redirect traffic and to host exploit kits.(Citation: Gigamon Berserk Bear October 2021) [Gigamon Berserk Bear October 2021](https://vblocalhost.com/uploads/VB2021-Slowik.pdf)
- [G0046 - FIN7](../../../../Threat%20Intelligence/Groups/G0046%20-%20FIN7.md) — [FIN7](https://attack.mitre.org/groups/G0046) has compromised a digital product website and modified multiple download links to point to trojanized versions of offered digital products.(Citation: Mandiant FIN7 Apr 2022) [Mandiant FIN7 Apr 2022](https://www.mandiant.com/resources/evolution-of-fin7)
- [G1014 - LuminousMoth](../../../../Threat%20Intelligence/Groups/G1014%20-%20LuminousMoth.md) — [LuminousMoth](https://attack.mitre.org/groups/G1014) has redirected compromised machines to an actor-controlled webpage through HTML injection.(Citation: Bitdefender LuminousMoth July 2021) [Bitdefender LuminousMoth July 2021](https://www.bitdefender.com/blog/labs/luminousmoth-plugx-file-exfiltration-and-persistence-revisited)
- [G1020 - Mustard Tempest](../../../../Threat%20Intelligence/Groups/G1020%20-%20Mustard%20Tempest.md) — [Mustard Tempest](https://attack.mitre.org/groups/G1020) has injected malicious JavaScript into compromised websites to infect victims via drive-by download.(Citation: SocGholish-update)(Citation: SentinelOne SocGholish Infrastructure November 2022)(Citation: Red Canary SocGholish March 2024)(Citation: Secureworks Gold Prelude Profile) [SocGholish-update](https://www.proofpoint.com/us/blog/threat-insight/part-1-socgholish-very-real-threat-very-fake-update) · [SentinelOne SocGholish Infrastructure November 2022](https://www.sentinelone.com/labs/socgholish-diversifies-and-expands-its-malware-staging-infrastructure-to-counter-defenders/) · [Red Canary SocGholish March 2024](https://redcanary.com/threat-detection-report/threats/socgholish/) · [Secureworks Gold Prelude Profile](https://www.secureworks.com/research/threat-profiles/gold-prelude)
- [G0027 - Threat Group-3390](../../../../Threat%20Intelligence/Groups/G0027%20-%20Threat%20Group-3390.md) — [Threat Group-3390](https://attack.mitre.org/groups/G0027) has embedded malicious code into websites to screen a potential victim's IP address and then exploit their browser if they are of interest.(Citation: Gallagher 2015) [Gallagher 2015](http://arstechnica.com/security/2015/08/newly-discovered-chinese-hacking-group-hacked-100-websites-to-use-as-watering-holes/)
- [G0134 - Transparent Tribe](../../../../Threat%20Intelligence/Groups/G0134%20-%20Transparent%20Tribe.md) — [Transparent Tribe](https://attack.mitre.org/groups/G0134) has set up websites with malicious hyperlinks and iframes to infect targeted victims with [Crimson](https://attack.mitre.org/software/S0115), [njRAT](https://attack.mitre.org/software/S0385), and other malicious tools.(Citation: Proofpoint Operation Transparent Tribe March 2016)(Citation: Unit 42 ProjectM March 2016)(Citation: Talos Transparent Tribe May 2021) [Proofpoint Operation Transparent Tribe March 2016](https://www.proofpoint.com/sites/default/files/proofpoint-operation-transparent-tribe-threat-insight-en.pdf) · [Unit 42 ProjectM March 2016](https://unit42.paloaltonetworks.com/unit42-projectm-link-found-between-pakistani-actor-and-operation-transparent-tribe/) · [Talos Transparent Tribe May 2021](https://blog.talosintelligence.com/2021/05/transparent-tribe-infra-and-targeting.html)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0825 - Detection of Drive-by Target](../../../../Defenses/Detection%20Strategies/DET0825%20-%20Detection%20of%20Drive-by%20Target.md)

## Sources

- [ATT ScanBox](https://cybersecurity.att.com/blogs/labs-research/scanbox-a-reconnaissance-framework-used-on-watering-hole-attacks)
- [Gallagher 2015](http://arstechnica.com/security/2015/08/newly-discovered-chinese-hacking-group-hacked-100-websites-to-use-as-watering-holes/)
- [FireEye CFR Watering Hole 2012](https://web.archive.org/web/20201024230407/https://www.fireeye.com/blog/threat-research/2012/12/council-foreign-relations-water-hole-attack-details.html)
