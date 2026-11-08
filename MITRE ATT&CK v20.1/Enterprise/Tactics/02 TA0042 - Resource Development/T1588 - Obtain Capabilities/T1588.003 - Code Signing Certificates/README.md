# T1588.003 - Code Signing Certificates

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1588 - Obtain Capabilities](../README.md)

Adversaries may buy and/or steal code signing certificates that can be used during targeting. Code signing is the process of digitally signing executables and scripts to confirm the software author and guarantee that the code has not been altered or corrupted. Code signing provides a level of authenticity for a program from the developer and a guarantee that the program has not been tampered with.(Citation: Wikipedia Code Signing) Users and/or security tools may trust a signed piece of code more than an unsigned piece of code even if they don't know who issued the certificate or who the author is.

Prior to [Code Signing](https://attack.mitre.org/techniques/T1553/002), adversaries may purchase or steal code signing certificates for use in operations. The purchase of code signing certificates may be done using a front organization or using information stolen from a previously compromised entity that allows the adversary to validate to a certificate provider as that entity. Adversaries may also steal code signing materials directly from a compromised third-party.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1588/003)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [C0040 - APT41 DUST](../../../../Threat%20Intelligence/Campaigns/C0040%20-%20APT41%20DUST.md) — [APT41 DUST](https://attack.mitre.org/campaigns/C0040) used stolen code signing certificates to sign [DUSTTRAP](https://attack.mitre.org/software/S1159) malware and components.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
- [G0098 - BlackTech](../../../../Threat%20Intelligence/Groups/G0098%20-%20BlackTech.md) — [BlackTech](https://attack.mitre.org/groups/G0098) has used stolen code-signing certificates for its malicious payloads.(Citation: Symantec Palmerworm Sep 2020) [Symantec Palmerworm Sep 2020](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/palmerworm-blacktech-espionage-apt)
- [G0061 - FIN8](../../../../Threat%20Intelligence/Groups/G0061%20-%20FIN8.md) — [FIN8](https://attack.mitre.org/groups/G0061) has used an expired open-source X.509 certificate for testing in the OpenSSL repository, to connect to actor-controlled C2 servers.(Citation: Bitdefender Sardonic Aug 2021) [Bitdefender Sardonic Aug 2021](https://www.bitdefender.com/files/News/CaseStudies/study/401/Bitdefender-PR-Whitepaper-FIN8-creat5619-en-EN.pdf)
- [C0038 - HomeLand Justice](../../../../Threat%20Intelligence/Campaigns/C0038%20-%20HomeLand%20Justice.md) — During [HomeLand Justice](https://attack.mitre.org/campaigns/C0038), threat actors used tools with legitimate code signing certificates. (Citation: CISA Iran Albanian Attacks September 2022) [CISA Iran Albanian Attacks September 2022](https://www.cisa.gov/news-events/cybersecurity-advisories/aa22-264a)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has stolen a valid certificate that is used to sign the malware and the dropper.(Citation: S2W Troll Stealer 2024) [S2W Troll Stealer 2024](https://medium.com/s2wblog/kimsuky-disguised-as-a-korean-company-signed-with-a-valid-certificate-to-distribute-troll-stealer-cfa5d54314e2)
- [S0576 - MegaCortex](../../../../Threat%20Intelligence/Software/Malware/S0576%20-%20MegaCortex.md) — [MegaCortex](https://attack.mitre.org/software/S0576) has used code signing certificates issued to fake companies to bypass security controls.(Citation: IBM MegaCortex) [IBM MegaCortex](https://securityintelligence.com/posts/from-mega-to-giga-cross-version-comparison-of-top-megacortex-modifications/)
- [G0129 - Mustang Panda](../../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has used revoked code signing certificates for its malicious payloads.(Citation: Zscaler PAKLOG CorkLog SplatCloak Splatdropper April 2025) [Zscaler PAKLOG CorkLog SplatCloak Splatdropper April 2025](https://www.zscaler.com/blogs/security-research/latest-mustang-panda-arsenal-paklog-corklog-and-splatcloak-p2)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has obtained and utilized valid digital signatures via SSL[.]com.(Citation: CheckPoint_NimbusManticore_May2026)(Citation: CheckPoint_NimbusManticoreEurope_Sept2025)(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [CheckPoint_NimbusManticoreEurope_Sept2025](https://research.checkpoint.com/2025/nimbus-manticore-deploys-new-malware-targeting-europe/) · [CheckPoint_NimbusManticore_May2026](https://research.checkpoint.com/2026/fast-and-furious-nimbus-manticore-operations-during-the-iranian-conflict/) · [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [G0049 - OilRig](../../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has obtained stolen code signing certificates to digitally sign malware.(Citation: ClearSky OilRig Jan 2017) [ClearSky OilRig Jan 2017](http://www.clearskysec.com/oilrig/)
- [C0022 - Operation Dream Job](../../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — During [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) used code signing certificates issued by Sectigo RSA for some of its malware and tools.(Citation: ESET Lazarus Jun 2020) [ESET Lazarus Jun 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_Operation_Interception.pdf)
- [G0027 - Threat Group-3390](../../../../Threat%20Intelligence/Groups/G0027%20-%20Threat%20Group-3390.md) — [Threat Group-3390](https://attack.mitre.org/groups/G0027) has obtained stolen valid certificates, including from VMProtect and the Chinese instant messaging application Youdu, for their operations.(Citation: Lunghi Iron Tiger Linux) [Lunghi Iron Tiger Linux](https://www.trendmicro.com/en_us/research/23/c/iron-tiger-sysupdate-adds-linux-targeting.html)
- [G0102 - Wizard Spider](../../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has obtained code signing certificates signed by DigiCert, GlobalSign, and COMOOD for malware payloads.(Citation: DFIR Ryuk 2 Hour Speed Run November 2020)(Citation: Mandiant FIN12 Oct 2021) [Mandiant FIN12 Oct 2021](https://web.archive.org/web/20220313061955/https://www.mandiant.com/sites/default/files/2021-10/fin12-group-profile.pdf) · [DFIR Ryuk 2 Hour Speed Run November 2020](https://thedfirreport.com/2020/11/05/ryuk-speed-run-2-hours-to-ransom/)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0875 - Detection of Code Signing Certificates](../../../../Defenses/Detection%20Strategies/DET0875%20-%20Detection%20of%20Code%20Signing%20Certificates.md)

## Sources

- [Wikipedia Code Signing](https://en.wikipedia.org/wiki/Code_signing)
