# T1564.004 - NTFS File Attributes

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1564 - Hide Artifacts](../README.md)

Adversaries may use NTFS file attributes to hide their malicious data in order to evade detection. Every New Technology File System (NTFS) formatted partition contains a Master File Table (MFT) that maintains a record for every file/directory on the partition.(Citation: SpectorOps Host-Based Jul 2017) Within MFT entries are file attributes,(Citation: Microsoft NTFS File Attributes Aug 2010) such as Extended Attributes (EA) and Data [known as Alternate Data Streams (ADSs) when more than one Data attribute is present], that can be used to store arbitrary data (and even complete files).(Citation: SpectorOps Host-Based Jul 2017)(Citation: Microsoft File Streams)(Citation: MalwareBytes ADS July 2015)(Citation: Microsoft ADS Mar 2014)

Adversaries may store malicious data or binaries in file attribute metadata instead of directly in files. This may be done to evade some defenses, such as static indicator scanning tools and anti-virus.(Citation: Journey into IR ZeroAccess NTFS EA)(Citation: MalwareBytes ADS July 2015)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564/004)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0432 - Detection Strategy for NTFS File Attribute Abuse (ADS/EAs)](../../../../Defenses/Detection%20Strategies/DET0432%20-%20Detection%20Strategy%20for%20NTFS%20File%20Attribute%20Abuse%20%28ADS%20-%20EAs%29.md)

## Procedure examples

- [S0504 - Anchor](../../../../Threat%20Intelligence/Software/Malware/S0504%20-%20Anchor.md) — [Anchor](https://attack.mitre.org/software/S0504) has used NTFS to hide files.(Citation: Cyberreason Anchor December 2019) [Cyberreason Anchor December 2019](https://www.cybereason.com/blog/dropping-anchor-from-a-trickbot-infection-to-the-discovery-of-the-anchor-malware)
- [G0050 - APT32](../../../../Threat%20Intelligence/Groups/G0050%20-%20APT32.md) — [APT32](https://attack.mitre.org/groups/G0050) used NTFS alternate data streams to hide their payloads.(Citation: Cybereason Cobalt Kitty 2017) [Cybereason Cobalt Kitty 2017](https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf)
- [S0373 - Astaroth](../../../../Threat%20Intelligence/Software/Malware/S0373%20-%20Astaroth.md) — [Astaroth](https://attack.mitre.org/software/S0373) can abuse alternate data streams (ADS) to store content for malicious payloads.(Citation: Securelist Brazilian Banking Malware July 2020) [Securelist Brazilian Banking Malware July 2020](https://securelist.com/the-tetrade-brazilian-banking-malware/97779/)
- [S0570 - BitPaymer](../../../../Threat%20Intelligence/Software/Malware/S0570%20-%20BitPaymer.md) — [BitPaymer](https://attack.mitre.org/software/S0570) has copied itself to the <code>:bin</code> alternate data stream of a newly created file.(Citation: Crowdstrike Indrik November 2018) [Crowdstrike Indrik November 2018](https://www.crowdstrike.com/blog/big-game-hunting-the-evolution-of-indrik-spider-from-dridex-wire-fraud-to-bitpaymer-targeted-ransomware/)
- [S1052 - DEADEYE](../../../../Threat%20Intelligence/Software/Malware/S1052%20-%20DEADEYE.md) — The DEADEYE.EMBED variant of [DEADEYE](https://attack.mitre.org/software/S1052) can embed its payload in an alternate data stream of a local file.(Citation: Mandiant APT41) [Mandiant APT41](https://www.mandiant.com/resources/apt41-us-state-governments)
- [S0404 - esentutl](../../../../Threat%20Intelligence/Software/Tools/S0404%20-%20esentutl.md) — [esentutl](https://attack.mitre.org/software/S0404) can be used to read and write alternate data streams.(Citation: LOLBAS Esentutl) [LOLBAS Esentutl](https://lolbas-project.github.io/lolbas/Binaries/Esentutl/)
- [S0361 - Expand](../../../../Threat%20Intelligence/Software/Tools/S0361%20-%20Expand.md) — [Expand](https://attack.mitre.org/software/S0361) can be used to download or copy a file into an alternate data stream.(Citation: LOLBAS Expand) [LOLBAS Expand](https://lolbas-project.github.io/lolbas/Binaries/Expand/)
- [S0168 - Gazer](../../../../Threat%20Intelligence/Software/Malware/S0168%20-%20Gazer.md) — [Gazer](https://attack.mitre.org/software/S0168) stores configuration items in alternate data streams (ADSs) if the Registry is not accessible.(Citation: ESET Gazer Aug 2017) [ESET Gazer Aug 2017](https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf)
- [S1160 - Latrodectus](../../../../Threat%20Intelligence/Software/Malware/S1160%20-%20Latrodectus.md) — [Latrodectus](https://attack.mitre.org/software/S1160) can delete itself while its process is still running through the use of an alternate data stream.(Citation: Elastic Latrodectus May 2024) [Elastic Latrodectus May 2024](https://www.elastic.co/security-labs/spring-cleaning-with-latrodectus)
- [S0397 - LoJax](../../../../Threat%20Intelligence/Software/Malware/S0397%20-%20LoJax.md) — [LoJax](https://attack.mitre.org/software/S0397) has loaded an embedded NTFS DXE driver to be able to access and write to NTFS partitions.(Citation: ESET LoJax Sept 2018) [ESET LoJax Sept 2018](https://www.welivesecurity.com/wp-content/uploads/2018/09/ESET-LoJax.pdf)
- [S0139 - PowerDuke](../../../../Threat%20Intelligence/Software/Malware/S0139%20-%20PowerDuke.md) — [PowerDuke](https://attack.mitre.org/software/S0139) hides many of its backdoor payloads in an alternate data stream (ADS).(Citation: Volexity PowerDuke November 2016) [Volexity PowerDuke November 2016](https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/)
- [S0145 - POWERSOURCE](../../../../Threat%20Intelligence/Software/Malware/S0145%20-%20POWERSOURCE.md) — If the victim is using PowerShell 3.0 or later, [POWERSOURCE](https://attack.mitre.org/software/S0145) writes its decoded payload to an alternate data stream (ADS) named kernel32.dll that is saved in <code>%PROGRAMDATA%\Windows\</code>.(Citation: Cisco DNSMessenger March 2017) [Cisco DNSMessenger March 2017](http://blog.talosintelligence.com/2017/03/dnsmessenger.html)
- [S0019 - Regin](../../../../Threat%20Intelligence/Software/Malware/S0019%20-%20Regin.md) — The [Regin](https://attack.mitre.org/software/S0019) malware platform uses Extended Attributes to store encrypted executables.(Citation: Kaspersky Regin) [Kaspersky Regin](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070305/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf)
- [S0476 - Valak](../../../../Threat%20Intelligence/Software/Malware/S0476%20-%20Valak.md) — [Valak](https://attack.mitre.org/software/S0476) has the ability save and execute files as alternate data streams (ADS).(Citation: Cybereason Valak May 2020)(Citation: Unit 42 Valak July 2020)(Citation: SentinelOne Valak June 2020) [Unit 42 Valak July 2020](https://unit42.paloaltonetworks.com/valak-evolution/) · [SentinelOne Valak June 2020](https://assets.sentinelone.com/labs/sentinel-one-valak-i) · [Cybereason Valak May 2020](https://www.cybereason.com/blog/valak-more-than-meets-the-eye)
- [S0612 - WastedLocker](../../../../Threat%20Intelligence/Software/Malware/S0612%20-%20WastedLocker.md) — [WastedLocker](https://attack.mitre.org/software/S0612) has the ability to save and execute files as an alternate data stream (ADS).(Citation: Sentinel Labs WastedLocker July 2020) [Sentinel Labs WastedLocker July 2020](https://www.sentinelone.com/labs/wastedlocker-ransomware-abusing-ads-and-ntfs-file-attributes/)
- [S0027 - Zeroaccess](../../../../Threat%20Intelligence/Software/Malware/S0027%20-%20Zeroaccess.md) — Some variants of the [Zeroaccess](https://attack.mitre.org/software/S0027) Trojan have been known to store data in Extended Attributes.(Citation: Ciubotariu 2014) [Ciubotariu 2014](http://www.symantec.com/connect/blogs/trojanzeroaccessc-hidden-ntfs-ea)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Consider adjusting read and write permissions for NTFS EA, though this should be tested to ensure routine OS operations are not impeded. (Citation: InsiderThreat NTFS EA Oct 2017) [InsiderThreat NTFS EA Oct 2017](https://blog.stealthbits.com/attack-step-3-persistence-ntfs-extended-attributes-file-system-attacks)

## Sources

- [MalwareBytes ADS July 2015](https://blog.malwarebytes.com/101/2015/07/introduction-to-alternate-data-streams/)
- [SpectorOps Host-Based Jul 2017](https://posts.specterops.io/host-based-threat-modeling-indicator-design-a9dbbb53d5ea)
- [Journey into IR ZeroAccess NTFS EA](http://journeyintoir.blogspot.com/2012/12/extracting-zeroaccess-from-ntfs.html)
- [Microsoft NTFS File Attributes Aug 2010](https://blogs.technet.microsoft.com/askcore/2010/08/25/ntfs-file-attributes/)
- [Microsoft ADS Mar 2014](https://blogs.technet.microsoft.com/askcore/2013/03/24/alternate-data-streams-in-ntfs/)
- [Microsoft File Streams](https://learn.microsoft.com/en-us/windows/win32/fileio/file-streams)
