# T1560.002 - Archive via Library

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1560 - Archive Collected Data](../README.md)

An adversary may compress or encrypt data that is collected prior to exfiltration using 3rd party libraries. Many libraries exist that can archive data, including [Python](https://attack.mitre.org/techniques/T1059/006) rarfile,(Citation: PyPI RAR) libzip,(Citation: libzip) and zlib.(Citation: Zlib Github) Most libraries include functionality to encrypt and/or compress data.

Some archival libraries are preinstalled on systems, such as bzip2 on macOS and Linux, and zip on Windows. Note that the libraries are different from the utilities. The libraries can be linked against when compiling, while the utilities require spawning a subshell, or a similar execution mechanism.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1560/002)

**Tactics**  [Collection](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0642 - BADFLICK](../../../../Threat%20Intelligence/Software/Malware/S0642%20-%20BADFLICK.md) — [BADFLICK](https://attack.mitre.org/software/S0642) has compressed data using the aPLib compression library.(Citation: Accenture MUDCARP March 2019) [Accenture MUDCARP March 2019](https://web.archive.org/web/20210722005437/https://www.accenture.com/_acnmedia/PDF-96/Accenture-Security-MUDCARP.pdf)
- [S0127 - BBSRAT](../../../../Threat%20Intelligence/Software/Malware/S0127%20-%20BBSRAT.md) — [BBSRAT](https://attack.mitre.org/software/S0127) can compress data with ZLIB prior to sending it back to the C2 server.(Citation: Palo Alto Networks BBSRAT) [Palo Alto Networks BBSRAT](http://researchcenter.paloaltonetworks.com/2015/12/bbsrat-attacks-targeting-russian-organizations-linked-to-roaming-tiger/)
- [S0348 - Cardinal RAT](../../../../Threat%20Intelligence/Software/Malware/S0348%20-%20Cardinal%20RAT.md) — [Cardinal RAT](https://attack.mitre.org/software/S0348) applies compression to C2 traffic using the ZLIB library.(Citation: PaloAlto CardinalRat Apr 2017) [PaloAlto CardinalRat Apr 2017](https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/)
- [S0354 - Denis](../../../../Threat%20Intelligence/Software/Malware/S0354%20-%20Denis.md) — [Denis](https://attack.mitre.org/software/S0354) compressed collected data using zlib.(Citation: Securelist Denis April 2017) [Securelist Denis April 2017](https://securelist.com/use-of-dns-tunneling-for-cc-communications/78203/)
- [S0091 - Epic](../../../../Threat%20Intelligence/Software/Malware/S0091%20-%20Epic.md) — [Epic](https://attack.mitre.org/software/S0091) compresses the collected data with bzip2 before sending it to the C2 server.(Citation: Kaspersky Turla Aug 2014) [Kaspersky Turla Aug 2014](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08080105/KL_Epic_Turla_Technical_Appendix_20140806.pdf)
- [S0661 - FoggyWeb](../../../../Threat%20Intelligence/Software/Malware/S0661%20-%20FoggyWeb.md) — [FoggyWeb](https://attack.mitre.org/software/S0661) can invoke the `Common.Compress` method to compress data with the C# GZipStream compression class.(Citation: MSTIC FoggyWeb September 2021) [MSTIC FoggyWeb September 2021](https://www.microsoft.com/security/blog/2021/09/27/foggyweb-targeted-nobelium-malware-leads-to-persistent-backdoor/)
- [S1044 - FunnyDream](../../../../Threat%20Intelligence/Software/Malware/S1044%20-%20FunnyDream.md) — [FunnyDream](https://attack.mitre.org/software/S1044) has compressed collected files with zLib.(Citation: Bitdefender FunnyDream Campaign November 2020) [Bitdefender FunnyDream Campaign November 2020](https://www.bitdefender.com/files/News/CaseStudies/study/379/Bitdefender-Whitepaper-Chinese-APT.pdf)
- [S0260 - InvisiMole](../../../../Threat%20Intelligence/Software/Malware/S0260%20-%20InvisiMole.md) — [InvisiMole](https://attack.mitre.org/software/S0260) can use zlib to compress and decompress data.(Citation: ESET InvisiMole June 2018)(Citation: ESET InvisiMole June 2020) [ESET InvisiMole June 2018](https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/) · [ESET InvisiMole June 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_InvisiMole.pdf)
- [G0032 - Lazarus Group](../../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) malware IndiaIndia saves information gathered about the victim to a file that is compressed with Zlib, encrypted, and uploaded to a C2 server.(Citation: Novetta Blockbuster RATs)(Citation: McAfee Lazarus Resurfaces Feb 2018) [Novetta Blockbuster RATs](https://web.archive.org/web/20220608001455/https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf) · [McAfee Lazarus Resurfaces Feb 2018](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/)
- [S1141 - LunarWeb](../../../../Threat%20Intelligence/Software/Malware/S1141%20-%20LunarWeb.md) — [LunarWeb](https://attack.mitre.org/software/S1141) can zlib-compress data prior to exfiltration.(Citation: ESET Turla Lunar toolset May 2024) [ESET Turla Lunar toolset May 2024](https://www.welivesecurity.com/en/eset-research/moon-backdoors-lunar-landing-diplomatic-missions/)
- [S0352 - OSX_OCEANLOTUS.D](../../../../Threat%20Intelligence/Software/Malware/S0352%20-%20OSX_OCEANLOTUS.D.md) — [OSX_OCEANLOTUS.D](https://attack.mitre.org/software/S0352) scrambles and encrypts data using AES256 before sending it to the C2 server.(Citation: TrendMicro MacOS April 2018)(Citation: Trend Micro MacOS Backdoor November 2020) [TrendMicro MacOS April 2018](https://blog.trendmicro.com/trendlabs-security-intelligence/new-macos-backdoor-linked-to-oceanlotus-found/) · [Trend Micro MacOS Backdoor November 2020](https://www.trendmicro.com/en_us/research/20/k/new-macos-backdoor-connected-to-oceanlotus-surfaces.html)
- [S0053 - SeaDuke](../../../../Threat%20Intelligence/Software/Malware/S0053%20-%20SeaDuke.md) — [SeaDuke](https://attack.mitre.org/software/S0053) compressed data with zlib prior to sending it over C2.(Citation: Mandiant No Easy Breach) [Mandiant No Easy Breach](https://www.slideshare.net/slideshow/no-easy-breach-derby-con-2016/66447908)
- [G1057 - ShinyHunters](../../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has used the following command to compress collected data: ` pv -s "$(du -sb exfil | awk '{print $1}')" | zstd -3 -T0 -o exfil.tar.zst `.(Citation: Google_SHOracle_Jun2026) [Google_SHOracle_Jun2026](https://cloud.google.com/blog/topics/threat-intelligence/shinyhunters-targets-education-sector-oracle-exploit)
- [S0467 - TajMahal](../../../../Threat%20Intelligence/Software/Malware/S0467%20-%20TajMahal.md) — [TajMahal](https://attack.mitre.org/software/S0467) has the ability to use the open source libraries XZip/Xunzip and zlib to compress files.(Citation: Kaspersky TajMahal April 2019) [Kaspersky TajMahal April 2019](https://securelist.com/project-tajmahal/90240/)
- [G0027 - Threat Group-3390](../../../../Threat%20Intelligence/Groups/G0027%20-%20Threat%20Group-3390.md) — [Threat Group-3390](https://attack.mitre.org/groups/G0027) has used RAR to compress, encrypt, and password-protect files prior to exfiltration.(Citation: SecureWorks BRONZE UNION June 2017) [SecureWorks BRONZE UNION June 2017](https://www.secureworks.com/research/bronze-union)
- [S0086 - ZLib](../../../../Threat%20Intelligence/Software/Malware/S0086%20-%20ZLib.md) — The [ZLib](https://attack.mitre.org/software/S0086) backdoor compresses communications using the standard Zlib compression library.(Citation: Cylance Dust Storm) [Cylance Dust Storm](https://s7d2.scene7.com/is/content/cylance/prod/cylance-web/en-us/resources/knowledge-center/resource-library/reports/Op_Dust_Storm_Report.pdf)

## Detection strategies

- [DET0268 - Detect Archiving via Library (T1560.002)](../../../../Defenses/Detection%20Strategies/DET0268%20-%20Detect%20Archiving%20via%20Library%20%28T1560.002%29.md)

## Sources

- [libzip](https://libzip.org/)
- [Zlib Github](https://github.com/madler/zlib)
- [PyPI RAR](https://pypi.org/project/rarfile/)
