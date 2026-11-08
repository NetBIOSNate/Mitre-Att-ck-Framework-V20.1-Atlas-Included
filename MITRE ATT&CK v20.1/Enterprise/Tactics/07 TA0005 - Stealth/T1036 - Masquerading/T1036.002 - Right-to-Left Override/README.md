# T1036.002 - Right-to-Left Override

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

Adversaries may abuse the right-to-left override (RTLO or RLO) character (U+202E) to disguise a string and/or file name to make it appear benign. RTLO is a non-printing Unicode character that causes the text that follows it to be displayed in reverse. For example, a Windows screensaver executable named <code>March 25 \u202Excod.scr</code> will display as <code>March 25 rcs.docx</code>. A JavaScript file named <code>photo_high_re\u202Egnp.js</code> will be displayed as <code>photo_high_resj.png</code>.(Citation: Infosecinstitute RTLO Technique)

Adversaries may abuse the RTLO character as a means of tricking a user into executing what they think is a benign file type. A common use of this technique is with [Spearphishing Attachment](https://attack.mitre.org/techniques/T1566/001)/[Malicious File](https://attack.mitre.org/techniques/T1204/002) since it can trick both end users and defenders if they are not aware of how their tools display and render the RTLO character. Use of the RTLO character has been seen in many targeted intrusion attempts and criminal activity.(Citation: Trend Micro PLEAD RTLO)(Citation: Kaspersky RTLO Cyber Crime) RTLO can be used in the Windows Registry as well, where regedit.exe displays the reversed characters but the command line tool reg.exe does not by default.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/002)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0527 - Right-to-Left Override Masquerading Detection via Filename and Execution Context](../../../../Defenses/Detection%20Strategies/DET0527%20-%20Right-to-Left%20Override%20Masquerading%20Detection%20via%20Filename%20and%20Execution%20Context.md)

## Procedure examples

- [G0098 - BlackTech](../../../../Threat%20Intelligence/Groups/G0098%20-%20BlackTech.md) — [BlackTech](https://attack.mitre.org/groups/G0098) has used right-to-left-override to obfuscate the filenames of malicious e-mail attachments.(Citation: TrendMicro BlackTech June 2017) [TrendMicro BlackTech June 2017](https://blog.trendmicro.com/trendlabs-security-intelligence/following-trail-blacktech-cyber-espionage-campaigns/)
- [G0060 - BRONZE BUTLER](../../../../Threat%20Intelligence/Groups/G0060%20-%20BRONZE%20BUTLER.md) — [BRONZE BUTLER](https://attack.mitre.org/groups/G0060) has used Right-to-Left Override to deceive victims into executing several strains of malware.(Citation: Trend Micro Tick November 2019) [Trend Micro Tick November 2019](https://documents.trendmicro.com/assets/pdf/Operation-ENDTRADE-TICK-s-Multi-Stage-Backdoors-for-Attacking-Industries-and-Stealing-Classified-Data.pdf)
- [G0137 - Ferocious Kitten](../../../../Threat%20Intelligence/Groups/G0137%20-%20Ferocious%20Kitten.md) — [Ferocious Kitten](https://attack.mitre.org/groups/G0137) has used right-to-left override to reverse executables’ names to make them appear to have different file extensions, rather than their real ones.(Citation: Kaspersky Ferocious Kitten Jun 2021) [Kaspersky Ferocious Kitten Jun 2021](https://securelist.com/ferocious-kitten-6-years-of-covert-surveillance-in-iran/102806/)
- [G0004 - Ke3chang](../../../../Threat%20Intelligence/Groups/G0004%20-%20Ke3chang.md) — [Ke3chang](https://attack.mitre.org/groups/G0004) has used the right-to-left override character in spearphishing attachment names to trick targets into executing .scr and .exe files.(Citation: Mandiant Operation Ke3chang November 2014) [Mandiant Operation Ke3chang November 2014](https://www.mandiant.com/resources/operation-ke3chang-targeted-attacks-against-ministries-of-foreign-affairs)
- [G0029 - Scarlet Mimic](../../../../Threat%20Intelligence/Groups/G0029%20-%20Scarlet%20Mimic.md) — [Scarlet Mimic](https://attack.mitre.org/groups/G0029) has used the right-to-left override character in self-extracting RAR archive spearphishing attachment file names.(Citation: Scarlet Mimic Jan 2016) [Scarlet Mimic Jan 2016](http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/)

## Sources

- [Trend Micro PLEAD RTLO](https://blog.trendmicro.com/trendlabs-security-intelligence/plead-targeted-attacks-against-taiwanese-government-agencies-2/)
- [Kaspersky RTLO Cyber Crime](https://securelist.com/zero-day-vulnerability-in-telegram/83800/)
- [Infosecinstitute RTLO Technique](https://web.archive.org/web/20151102094333/https://resources.infosecinstitute.com/spoof-using-right-to-left-override-rtlo-technique-2/)
