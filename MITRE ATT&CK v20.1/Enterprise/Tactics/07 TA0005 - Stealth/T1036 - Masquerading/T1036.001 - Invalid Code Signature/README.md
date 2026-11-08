# T1036.001 - Invalid Code Signature

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

Adversaries may attempt to mimic features of valid code signatures to increase the chance of deceiving a user, analyst, or tool. Code signing provides a level of authenticity on a binary from the developer and a guarantee that the binary has not been tampered with. Adversaries can copy the metadata and signature information from a signed program, then use it as a template for an unsigned program. Files with invalid code signatures will fail digital signature validation checks, but they may appear more legitimate to users and security tools may improperly handle these files.(Citation: Threatexpress MetaTwin 2017)

Unlike [Code Signing](https://attack.mitre.org/techniques/T1553/002), this activity will not result in a valid signature.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/001)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary also forged digital signatures of tax documents using a combination of 96 byte padded SHA-256 hash and base64-encoding resemble a legitimately signed PDF file.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G0067 - APT37](../../../../Threat%20Intelligence/Groups/G0067%20-%20APT37.md) — [APT37](https://attack.mitre.org/groups/G0067) has signed its malware with an invalid digital certificates listed as “Tencent Technology (Shenzhen) Company Limited.”(Citation: Securelist ScarCruft Jun 2016) [Securelist ScarCruft Jun 2016](https://securelist.com/operation-daybreak/75100/)
- [S0128 - BADNEWS](../../../../Threat%20Intelligence/Software/Malware/S0128%20-%20BADNEWS.md) — [BADNEWS](https://attack.mitre.org/software/S0128) is sometimes signed with an invalid Authenticode certificate in an apparent effort to make it look more legitimate.(Citation: TrendMicro Patchwork Dec 2017) [TrendMicro Patchwork Dec 2017](https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf)
- [S0666 - Gelsemium](../../../../Threat%20Intelligence/Software/Malware/S0666%20-%20Gelsemium.md) — [Gelsemium](https://attack.mitre.org/software/S0666) has used unverified signatures on malicious DLLs.(Citation: ESET Gelsemium June 2021) [ESET Gelsemium June 2021](https://www.welivesecurity.com/wp-content/uploads/2021/06/eset_gelsemium.pdf)
- [S0198 - NETWIRE](../../../../Threat%20Intelligence/Software/Malware/S0198%20-%20NETWIRE.md) — The [NETWIRE](https://attack.mitre.org/software/S0198) client has been signed by fake and invalid digital certificates.(Citation: McAfee Netwire Mar 2015) [McAfee Netwire Mar 2015](https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/)
- [S1050 - PcShare](../../../../Threat%20Intelligence/Software/Tools/S1050%20-%20PcShare.md) — [PcShare](https://attack.mitre.org/software/S1050) has used an invalid certificate in attempt to appear legitimate.(Citation: Bitdefender FunnyDream Campaign November 2020) [Bitdefender FunnyDream Campaign November 2020](https://www.bitdefender.com/files/News/CaseStudies/study/379/Bitdefender-Whitepaper-Chinese-APT.pdf)
- [S0019 - Regin](../../../../Threat%20Intelligence/Software/Malware/S0019%20-%20Regin.md) — [Regin](https://attack.mitre.org/software/S0019) stage 1 modules for 64-bit systems have been found to be signed with fake certificates masquerading as originating from Microsoft Corporation and Broadcom Corporation.(Citation: Kaspersky Regin) [Kaspersky Regin](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070305/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf)
- [S1234 - SplatCloak](../../../../Threat%20Intelligence/Software/Malware/S1234%20-%20SplatCloak.md) — [SplatCloak](https://attack.mitre.org/software/S1234) has used a revoked certificate to exploit Windows driver execution policy where certificates issued before a specific date could still load.(Citation: Zscaler PAKLOG CorkLog SplatCloak Splatdropper April 2025) [Zscaler PAKLOG CorkLog SplatCloak Splatdropper April 2025](https://www.zscaler.com/blogs/security-research/latest-mustang-panda-arsenal-paklog-corklog-and-splatcloak-p2)
- [G1058 - The Gentlemen](../../../../Threat%20Intelligence/Groups/G1058%20-%20The%20Gentlemen.md) — [The Gentlemen](https://attack.mitre.org/groups/G1058) has copied digital signatures from legitimate executables in attempts to circumvent detection.(Citation: SoučekESET_Gentlemen_Jun2026) [SoučekESET_Gentlemen_Jun2026](https://www.welivesecurity.com/en/eset-research/killing-me-gently-inside-gentlemens-edr-killer-framework/)
- [S9050 - Vidar](../../../../Threat%20Intelligence/Software/Malware/S9050%20-%20Vidar.md) — [Vidar](https://attack.mitre.org/software/S9050) has signed its DLL using fake certificates githab[.]com and grow[.]com.(Citation: Intrinsec_Vidar_April2026) [Vidar](https://attack.mitre.org/software/S9050) has also signed its files with an expired digital certificate.(Citation: QuorumCyber_Vidar_March2023) [Intrinsec_Vidar_April2026](https://www.intrinsec.com/wp-content/uploads/2026/04/TLP_CLEAR-20260424-New_Vidar.pdf) · [QuorumCyber_Vidar_March2023](https://www.quorumcyber.com/wp-content/uploads/2023/01/Malware-Analysis-Vidar.pdf)
- [G0112 - Windshift](../../../../Threat%20Intelligence/Groups/G0112%20-%20Windshift.md) — [Windshift](https://attack.mitre.org/groups/G0112) has used revoked certificates to sign malware.(Citation: objective-see windtail1 dec 2018)(Citation: SANS Windshift August 2018) [SANS Windshift August 2018](https://www.scribd.com/document/661837258/WINDSHIFT-summit-archive-1554718868) · [objective-see windtail1 dec 2018](https://objective-see.com/blog/blog_0x3B.html)
- [S0466 - WindTail](../../../../Threat%20Intelligence/Software/Malware/S0466%20-%20WindTail.md) — [WindTail](https://attack.mitre.org/software/S0466) has been incompletely signed with revoked certificates.(Citation: objective-see windtail1 dec 2018) [objective-see windtail1 dec 2018](https://objective-see.com/blog/blog_0x3B.html)

## Mitigations

- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Require signed binaries.

## Detection strategies

- [DET0031 - Invalid Code Signature Execution Detection via Metadata and Behavioral Context](../../../../Defenses/Detection%20Strategies/DET0031%20-%20Invalid%20Code%20Signature%20Execution%20Detection%20via%20Metadata%20and%20Behavioral%20Context.md)

## Sources

- [Threatexpress MetaTwin 2017](https://threatexpress.com/blogs/2017/metatwin-borrowing-microsoft-metadata-and-digital-signatures-to-hide-binaries/)
