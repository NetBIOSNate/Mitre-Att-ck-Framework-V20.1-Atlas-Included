# T1001.002 - Steganography

[Enterprise](../../../../README.md) / [Command and Control](../../README.md) / [T1001 - Data Obfuscation](../README.md)

Adversaries may use steganographic techniques to hide command and control traffic to make detection efforts more difficult. Steganographic techniques can be used to hide data in digital messages that are transferred between systems. This hidden information can be used for command and control of compromised systems. In some cases, the passing of files embedded using steganography, such as image or document files, can be used for command and control.(Citation: Kaspersky)(Citation: Sophos - Cover Their Tracks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1001/002)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md), [ESXi](../../../../Platforms/ESXi.md)

## Procedure examples

- [G0001 - Axiom](../../../../Threat%20Intelligence/Groups/G0001%20-%20Axiom.md) — [Axiom](https://attack.mitre.org/groups/G0001) has used steganography to hide its C2 communications.(Citation: Novetta-Axiom) [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)
- [S0187 - Daserf](../../../../Threat%20Intelligence/Software/Malware/S0187%20-%20Daserf.md) — [Daserf](https://attack.mitre.org/software/S0187) can use steganography to hide malicious code downloaded to the victim.(Citation: Trend Micro Daserf Nov 2017) [Trend Micro Daserf Nov 2017](http://blog.trendmicro.com/trendlabs-security-intelligence/redbaldknight-bronze-butler-daserf-backdoor-now-using-steganography/)
- [S0038 - Duqu](../../../../Threat%20Intelligence/Software/Malware/S0038%20-%20Duqu.md) — When the [Duqu](https://attack.mitre.org/software/S0038) command and control is operating over HTTP or HTTPS, Duqu uploads data to its controller by appending it to a blank JPG file.(Citation: Symantec W32.Duqu) [Symantec W32.Duqu](https://web.archive.org/web/20111213083345/https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf)
- [S0037 - HAMMERTOSS](../../../../Threat%20Intelligence/Software/Malware/S0037%20-%20HAMMERTOSS.md) — [HAMMERTOSS](https://attack.mitre.org/software/S0037) is controlled via commands that are appended to image files.(Citation: FireEye APT29) [FireEye APT29](https://services.google.com/fh/files/misc/rpt-apt29-hammertoss-stealthy-tactics-define-en.pdf)
- [S0395 - LightNeuron](../../../../Threat%20Intelligence/Software/Malware/S0395%20-%20LightNeuron.md) — [LightNeuron](https://attack.mitre.org/software/S0395) is controlled via commands that are embedded into PDFs and JPGs using steganographic methods.(Citation: ESET LightNeuron May 2019) [ESET LightNeuron May 2019](https://www.welivesecurity.com/wp-content/uploads/2019/05/ESET-LightNeuron.pdf)
- [S1142 - LunarMail](../../../../Threat%20Intelligence/Software/Malware/S1142%20-%20LunarMail.md) — [LunarMail](https://attack.mitre.org/software/S1142) can parse IDAT chunks from .png files to look for zlib-compressed and AES encrypted C2 commands.(Citation: ESET Turla Lunar toolset May 2024) [ESET Turla Lunar toolset May 2024](https://www.welivesecurity.com/en/eset-research/moon-backdoors-lunar-landing-diplomatic-missions/)
- [S1141 - LunarWeb](../../../../Threat%20Intelligence/Software/Malware/S1141%20-%20LunarWeb.md) — [LunarWeb](https://attack.mitre.org/software/S1141) can receive C2 commands hidden in the structure of .jpg and .gif images.(Citation: ESET Turla Lunar toolset May 2024) [ESET Turla Lunar toolset May 2024](https://www.welivesecurity.com/en/eset-research/moon-backdoors-lunar-landing-diplomatic-missions/)
- [C0023 - Operation Ghost](../../../../Threat%20Intelligence/Campaigns/C0023%20-%20Operation%20Ghost.md) — During [Operation Ghost](https://attack.mitre.org/campaigns/C0023), [APT29](https://attack.mitre.org/groups/G0016) used steganography to hide the communications between the implants and their C&C servers.(Citation: ESET Dukes October 2019) [ESET Dukes October 2019](https://www.welivesecurity.com/wp-content/uploads/2019/10/ESET_Operation_Ghost_Dukes.pdf)
- [S0495 - RDAT](../../../../Threat%20Intelligence/Software/Malware/S0495%20-%20RDAT.md) — [RDAT](https://attack.mitre.org/software/S0495) can process steganographic images attached to email messages to send and receive C2 commands. [RDAT](https://attack.mitre.org/software/S0495) can also embed additional messages within BMP images to communicate with the [RDAT](https://attack.mitre.org/software/S0495) operator.(Citation: Unit42 RDAT July 2020) [Unit42 RDAT July 2020](https://unit42.paloaltonetworks.com/oilrig-novel-c2-channel-steganography/)
- [S0633 - Sliver](../../../../Threat%20Intelligence/Software/Tools/S0633%20-%20Sliver.md) — [Sliver](https://attack.mitre.org/software/S0633) can encode binary data into a .PNG file for C2 communication.(Citation: GitHub Sliver HTTP) [GitHub Sliver HTTP](https://github.com/BishopFox/sliver/wiki/HTTP%28S%29-C2)
- [S0559 - SUNBURST](../../../../Threat%20Intelligence/Software/Malware/S0559%20-%20SUNBURST.md) — [SUNBURST](https://attack.mitre.org/software/S0559) C2 data attempted to appear as benign XML related to .NET assemblies or as a faux JSON blob.(Citation: FireEye SUNBURST Backdoor December 2020)(Citation: FireEye SUNBURST Additional Details Dec 2020)(Citation: Symantec Sunburst Sending Data January 2021) [FireEye SUNBURST Backdoor December 2020](https://www.fireeye.com/blog/threat-research/2020/12/evasive-attacker-leverages-solarwinds-supply-chain-compromises-with-sunburst-backdoor.html) · [FireEye SUNBURST Additional Details Dec 2020](https://www.fireeye.com/blog/threat-research/2020/12/sunburst-additional-technical-details.html) · [Symantec Sunburst Sending Data January 2021](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/solarwinds-sunburst-sending-data)
- [S0230 - ZeroT](../../../../Threat%20Intelligence/Software/Malware/S0230%20-%20ZeroT.md) — [ZeroT](https://attack.mitre.org/software/S0230) has retrieved stage 2 payloads as Bitmap images that use Least Significant Bit (LSB) steganography.(Citation: Proofpoint TA459 April 2017)(Citation: Proofpoint ZeroT Feb 2017) [Proofpoint TA459 April 2017](https://www.proofpoint.com/us/threat-insight/post/apt-targets-financial-analysts) · [Proofpoint ZeroT Feb 2017](https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx)
- [S0672 - Zox](../../../../Threat%20Intelligence/Software/Malware/S0672%20-%20Zox.md) — [Zox](https://attack.mitre.org/software/S0672) has used the .PNG file format for C2 communications.(Citation: Novetta-Axiom) [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)

## Detection strategies

- [DET0235 - Detecting Steganographic Command and Control via File + Network Correlation](../../../../Defenses/Detection%20Strategies/DET0235%20-%20Detecting%20Steganographic%20Command%20and%20Control%20via%20File%20%2B%20Network%20Correlation.md)

## Mitigations

- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate some obfuscation activity at the network level.

## Sources

- [Sophos - Cover Their Tracks](https://www.sophos.com/en-us/blog/cover-their-tracks-how-attackers-are-hiding-cc-communication)
- [Kaspersky](https://www.kaspersky.com/resource-center/definitions/what-is-steganography)
