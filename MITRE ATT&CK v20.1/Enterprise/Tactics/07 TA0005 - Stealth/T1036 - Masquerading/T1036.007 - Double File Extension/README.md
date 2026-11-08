# T1036.007 - Double File Extension

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

Adversaries may abuse a double extension in the filename as a means of masquerading the true file type. A file name may include a secondary file type extension that may cause only the first extension to be displayed (ex: <code>File.txt.exe</code> may render in some views as just <code>File.txt</code>). However, the second extension is the true file type that determines how the file is opened and executed. The real file extension may be hidden by the operating system in the file browser (ex: explorer.exe), as well as in any software configured using or similar to the system’s policies.(Citation: PCMag DoubleExtension)(Citation: SOCPrime DoubleExtension) 

Adversaries may abuse double extensions to attempt to conceal dangerous file types of payloads. A very common usage involves tricking a user into opening what they think is a benign file type but is actually executable code. Such files often pose as email attachments and allow an adversary to gain [Initial Access](https://attack.mitre.org/tactics/TA0001) into a user’s system via [Spearphishing Attachment](https://attack.mitre.org/techniques/T1566/001) then [User Execution](https://attack.mitre.org/techniques/T1204). For example, an executable file attachment named <code>Evil.txt.exe</code> may display as <code>Evil.txt</code> to a user. The user may then view it as a benign text file and open it, inadvertently executing the hidden malware.(Citation: SOCPrime DoubleExtension)

Common file types, such as text files (.txt, .doc, etc.) and image files (.jpg, .gif, etc.) are typically used as the first extension to appear benign. Executable extensions commonly regarded as dangerous, such as .exe, .lnk, .hta, and .scr, often appear as the second extension and true file type.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/007)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0534 - Bazar](../../../../Threat%20Intelligence/Software/Malware/S0534%20-%20Bazar.md) — The [Bazar](https://attack.mitre.org/software/S0534) loader has used dual-extension executable files such as PreviewReport.DOC.exe.(Citation: Cybereason Bazar July 2020) [Cybereason Bazar July 2020](https://www.cybereason.com/blog/a-bazar-of-tricks-following-team9s-development-cycles)
- [S1111 - DarkGate](../../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) masquerades malicious LNK files as PDF objects using the double extension <code>.pdf.lnk</code>.(Citation: Trellix Darkgate 2023) [Trellix Darkgate 2023](https://www.trellix.com/blogs/research/the-continued-evolution-of-the-darkgate-malware-as-a-service/)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used an additional filename extension to hide the true file type. [Kimsuky](https://attack.mitre.org/groups/G0094) has also masqueraded malicious LNK files as PDF objects using the double extension .pdf.lnk.(Citation: Securonix Kimsuky February 2025) [Securonix Kimsuky February 2025](https://www.securonix.com/blog/analyzing-deepdrive-north-korean-threat-actors-observed-exploiting-trusted-platforms-for-targeted-attacks/)
- [S1015 - Milan](../../../../Threat%20Intelligence/Software/Malware/S1015%20-%20Milan.md) — [Milan](https://attack.mitre.org/software/S1015) has used an executable named `companycatalog.exe.config` to appear benign.(Citation: ClearSky Siamesekitten August 2021) [ClearSky Siamesekitten August 2021](https://www.clearskysec.com/siamesekitten/)
- [G0129 - Mustang Panda](../../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has used an additional filename extension to hide the true file type.(Citation: Crowdstrike MUSTANG PANDA June 2018)(Citation: Anomali MUSTANG PANDA October 2019) [Crowdstrike MUSTANG PANDA June 2018](https://www.crowdstrike.com/blog/meet-crowdstrikes-adversary-of-the-month-for-june-mustang-panda/) · [Anomali MUSTANG PANDA October 2019](https://www.anomali.com/blog/china-based-apt-mustang-panda-targets-minority-groups-public-and-private-sector-organizations)

## Mitigations

- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Disable the default to “hide file extensions for known file types” in Windows OS.(Citation: Seqrite DoubleExtension)(Citation: HowToGeek ShowExtension) [Seqrite DoubleExtension](https://www.seqrite.com/blog/how-to-avoid-dual-attack-and-vulnerable-files-with-double-extension/) · [HowToGeek ShowExtension](https://www.howtogeek.com/205086/beginner-how-to-make-windows-show-file-extensions/)
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to look for double extensions in filenames, and in general use training as a way to bring awareness to common phishing and spearphishing techniques and how to raise suspicion for potentially malicious events.

## Detection strategies

- [DET0366 - Detection Strategy for Double File Extension Masquerading](../../../../Defenses/Detection%20Strategies/DET0366%20-%20Detection%20Strategy%20for%20Double%20File%20Extension%20Masquerading.md)

## Sources

- [SOCPrime DoubleExtension](https://socprime.com/blog/rule-of-the-week-possible-malicious-file-double-extension/)
- [PCMag DoubleExtension](https://www.pcmag.com/encyclopedia/term/double-extension)
