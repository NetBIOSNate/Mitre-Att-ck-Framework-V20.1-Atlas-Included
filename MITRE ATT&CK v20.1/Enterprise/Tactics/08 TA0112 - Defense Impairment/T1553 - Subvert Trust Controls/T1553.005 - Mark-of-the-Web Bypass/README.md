# T1553.005 - Mark-of-the-Web Bypass

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1553 - Subvert Trust Controls](../README.md)

Adversaries may abuse specific file formats to subvert Mark-of-the-Web (MOTW) controls. In Windows, when files are downloaded from the Internet, they are tagged with a hidden NTFS Alternate Data Stream (ADS) named <code>Zone.Identifier</code> with a specific value known as the MOTW.(Citation: Microsoft Zone.Identifier 2020) Files that are tagged with MOTW are protected and cannot perform certain actions. For example, starting in MS Office 10, if a MS Office file has the MOTW, it will open in Protected View. Executables tagged with the MOTW will be processed by Windows Defender SmartScreen that compares files with an allowlist of well-known executables. If the file is not known/trusted, SmartScreen will prevent the execution and warn the user not to run it.(Citation: Beek Use of VHD Dec 2020)(Citation: Outflank MotW 2020)(Citation: Intezer Russian APT Dec 2020)

Adversaries may abuse container files such as compressed/archive (.arj, .gzip) and/or disk image (.iso, .vhd) file formats to deliver malicious payloads that may not be tagged with MOTW. Container files downloaded from the Internet will be marked with MOTW but the files within may not inherit the MOTW after the container files are extracted and/or mounted. MOTW is an NTFS feature and many container files do not support NTFS alternative data streams. After a container file is extracted and/or mounted, the files contained within them may be treated as local files on disk and run without protections.(Citation: Beek Use of VHD Dec 2020)(Citation: Outflank MotW 2020)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1553/005)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S1025 - Amadey](../../../../Threat%20Intelligence/Software/Malware/S1025%20-%20Amadey.md) — [Amadey](https://attack.mitre.org/software/S1025) has modified the `:Zone.Identifier` in the ADS area to zero.(Citation: Korean FSI TA505 2020) [Korean FSI TA505 2020](https://www.fsec.or.kr/user/bbs/fsec/163/344/bbsDataView/1382.do?page=1&column=&search=&searchSDate=&searchEDate=&bbsDataCategory=)
- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has embedded ISO images and VHDX files in HTML to evade Mark-of-the-Web.(Citation: ESET T3 Threat Report 2021) [ESET T3 Threat Report 2021](https://www.welivesecurity.com/wp-content/uploads/2022/02/eset_threat_report_t32021.pdf)
- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has used ISO and VHD files to deploy malware and to bypass Mark-of-the-Web (MOTW) security measures.(Citation: 1 - appv) [1 - appv](https://securelist.com/bluenoroff-methods-bypass-motw/108383/)
- [S0650 - QakBot](../../../../Threat%20Intelligence/Software/Malware/S0650%20-%20QakBot.md) — [QakBot](https://attack.mitre.org/software/S0650) has been packaged in ISO files in order to bypass Mark of the Web (MOTW) security measures.(Citation: Trend Micro Black Basta October 2022) [Trend Micro Black Basta October 2022](https://www.trendmicro.com/en_us/research/22/j/black-basta-infiltrates-networks-via-qakbot-brute-ratel-and-coba.html)
- [G0092 - TA505](../../../../Threat%20Intelligence/Groups/G0092%20-%20TA505.md) — [TA505](https://attack.mitre.org/groups/G0092) has used .iso files to deploy malicious .lnk files.(Citation: TrendMicro TA505 Aug 2019) [TrendMicro TA505 Aug 2019](https://www.trendmicro.com/en_us/research/19/h/ta505-at-it-again-variety-is-the-spice-of-servhelper-and-flawedammyy.html)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider disabling auto-mounting of disk image files (i.e., .iso, .img, .vhd, and .vhdx). This can be achieved by modifying the Registry values related to the Windows Explorer file associations in order to disable the automatic Explorer "Mount and Burn" dialog for these file extensions. Note: this will not deactivate the mount functionality itself.(Citation: GitHub MOTW) [GitHub MOTW](https://gist.github.com/wdormann/fca29e0dcda8b5c0472e73e10c78c3e7)
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Consider blocking container file types at web and/or email gateways. Consider unregistering container file extensions in Windows File Explorer.(Citation: Dormann Dangers of VHD 2019) [Dormann Dangers of VHD 2019](https://insights.sei.cmu.edu/cert/2019/09/the-dangers-of-vhd-and-vhdx-files.html)

## Detection strategies

- [DET0257 - Detect Mark-of-the-Web (MOTW) Bypass via Container and Disk Image Files](../../../../Defenses/Detection%20Strategies/DET0257%20-%20Detect%20Mark-of-the-Web%20%28MOTW%29%20Bypass%20via%20Container%20and%20Disk%20Image%20Files.md)

## Sources

- [Beek Use of VHD Dec 2020](https://web.archive.org/web/20201203131725/https://christiaanbeek.medium.com/investigating-the-use-of-vhd-files-by-cybercriminals-3f1f08304316)
- [Outflank MotW 2020](https://outflank.nl/blog/2020/03/30/mark-of-the-web-from-a-red-teams-perspective/)
- [Intezer Russian APT Dec 2020](https://www.intezer.com/blog/research/russian-apt-uses-covid-19-lures-to-deliver-zebrocy/)
- [Microsoft Zone.Identifier 2020](https://docs.microsoft.com/en-us/openspecs/windows_protocols/ms-fscc/6e3f7352-d11c-4d76-8c39-2516a9df36e8)
