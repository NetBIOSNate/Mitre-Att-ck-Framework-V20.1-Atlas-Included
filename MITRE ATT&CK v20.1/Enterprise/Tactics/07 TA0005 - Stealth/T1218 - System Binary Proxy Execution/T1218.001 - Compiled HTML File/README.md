# T1218.001 - Compiled HTML File

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse Compiled HTML files (.chm) to conceal malicious code. CHM files are commonly distributed as part of the Microsoft HTML Help system. CHM files are compressed compilations of various content such as HTML documents, images, and scripting/web related programming languages such as VBA, JScript, Java, and ActiveX.(Citation: Microsoft HTML Help May 2018) CHM content is displayed using underlying components of the Internet Explorer browser(Citation: Microsoft HTML Help ActiveX) loaded by the HTML Help executable program (hh.exe).(Citation: Microsoft HTML Help Executable Program)

A custom CHM file containing embedded payloads could be delivered to a victim then triggered by [User Execution](https://attack.mitre.org/techniques/T1204). CHM execution may also bypass application control on older and/or unpatched systems that do not account for execution of binaries through hh.exe.(Citation: MsitPros CHM Aug 2017)(Citation: Microsoft CVE-2017-8625 Aug 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/001)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has used CHM files to move concealed payloads.(Citation: Kaspersky Lazarus Under The Hood APR 2017) [Kaspersky Lazarus Under The Hood APR 2017](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07180244/Lazarus_Under_The_Hood_PDF_final.pdf)
- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) used compiled HTML (.chm) files for targeting.(Citation: FireEye APT41 Aug 2019) [FireEye APT41 Aug 2019](https://www.mandiant.com/sites/default/files/2022-02/rt-apt41-dual-operation.pdf)
- [S0373 - Astaroth](../../../../Threat%20Intelligence/Software/Malware/S0373%20-%20Astaroth.md) — [Astaroth](https://attack.mitre.org/software/S0373) uses ActiveX objects for file execution and manipulation. (Citation: Cofense Astaroth Sept 2018) [Cofense Astaroth Sept 2018](https://web.archive.org/web/20200302071436/https://cofense.com/seeing-resurgence-demonic-astaroth-wmic-trojan/)
- [G0070 - Dark Caracal](../../../../Threat%20Intelligence/Groups/G0070%20-%20Dark%20Caracal.md) — [Dark Caracal](https://attack.mitre.org/groups/G0070) leveraged a compiled HTML file that contained a command to download and run an executable.(Citation: Lookout Dark Caracal Jan 2018) [Lookout Dark Caracal Jan 2018](https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf)
- [G0049 - OilRig](../../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has used a CHM payload to load and execute another malicious file once delivered to a victim.(Citation: Palo Alto OilRig May 2016) [Palo Alto OilRig May 2016](http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/)
- [G0091 - Silence](../../../../Threat%20Intelligence/Groups/G0091%20-%20Silence.md) — [Silence](https://attack.mitre.org/groups/G0091) has weaponized CHM files in their phishing campaigns.(Citation: Cyber Forensicator Silence Jan 2019)(Citation: SecureList Silence Nov 2017)(Citation: Group IB Silence Aug 2019)(Citation: Group IB Silence Sept 2018) [SecureList Silence Nov 2017](https://securelist.com/the-silence/83009/) · [Group IB Silence Sept 2018](https://go.group-ib.com/report-silence-en?_gl=1*d1bh3a*_ga*MTIwMzM5Mzc5MS4xNjk4OTI5NzY4*_ga_QMES53K3Y2*MTcwNDcyMjU2OS40LjEuMTcwNDcyMzU1Mi41My4wLjA.) · [Group IB Silence Aug 2019](https://www.group-ib.com/resources/threat-research/silence_2.0.going_global.pdf) · [Cyber Forensicator Silence Jan 2019](https://web.archive.org/web/20220119133748/https://cyberforensicator.com/2019/01/20/silence-dissecting-malicious-chm-files-and-performing-forensic-analysis/)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Consider using application control to prevent execution of hh.exe if it is not required for a given system or network to prevent potential misuse by adversaries.
- [M1021 - Restrict Web-Based Content](../../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — Consider blocking download/transfer and execution of potentially uncommon file types known to be used in adversary campaigns, such as CHM files

## Detection strategies

- [DET0342 - Detection of Suspicious Compiled HTML File Execution via hh.exe](../../../../Defenses/Detection%20Strategies/DET0342%20-%20Detection%20of%20Suspicious%20Compiled%20HTML%20File%20Execution%20via%20hh.exe.md)

## Sources

- [Microsoft CVE-2017-8625 Aug 2017](https://web.archive.org/web/20250419140549/https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2017-8625)
- [Microsoft HTML Help May 2018](https://docs.microsoft.com/previous-versions/windows/desktop/htmlhelp/microsoft-html-help-1-4-sdk)
- [Microsoft HTML Help Executable Program](https://msdn.microsoft.com/windows/desktop/ms524405)
- [Microsoft HTML Help ActiveX](https://msdn.microsoft.com/windows/desktop/ms644670)
- [MsitPros CHM Aug 2017](https://oddvar.moe/2017/08/13/bypassing-device-guard-umci-using-chm-cve-2017-8625/)
