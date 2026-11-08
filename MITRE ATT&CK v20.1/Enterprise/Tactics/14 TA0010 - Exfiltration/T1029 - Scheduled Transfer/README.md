# T1029 - Scheduled Transfer

[Enterprise](../../../README.md) / [Exfiltration](../README.md)

Adversaries may schedule data exfiltration to be performed only at certain times of day or at certain intervals. This could be done to blend traffic patterns with normal activity or availability.(Citation: Delay Code Execution in Java)

When scheduled exfiltration is used, other exfiltration techniques likely apply as well to transfer the information out of the network, such as [Exfiltration Over C2 Channel](https://attack.mitre.org/techniques/T1041) or [Exfiltration Over Alternative Protocol](https://attack.mitre.org/techniques/T1048).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1029)

**Tactics**  [Exfiltration](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S0045 - ADVSTORESHELL](../../../Threat%20Intelligence/Software/Malware/S0045%20-%20ADVSTORESHELL.md) — [ADVSTORESHELL](https://attack.mitre.org/software/S0045) collects, compresses, encrypts, and exfiltrates data to the C2 server every 10 minutes.(Citation: ESET Sednit Part 2) [ESET Sednit Part 2](http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf)
- [S0667 - Chrommme](../../../Threat%20Intelligence/Software/Malware/S0667%20-%20Chrommme.md) — [Chrommme](https://attack.mitre.org/software/S0667) can set itself to sleep before requesting a new command from C2.(Citation: ESET Gelsemium June 2021) [ESET Gelsemium June 2021](https://www.welivesecurity.com/wp-content/uploads/2021/06/eset_gelsemium.pdf)
- [S0154 - Cobalt Strike](../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) can set its Beacon payload to reach out to the C2 server on an arbitrary and random interval.(Citation: cobaltstrike manual) [cobaltstrike manual](https://web.archive.org/web/20210825130434/https://cobaltstrike.com/downloads/csmanual38.pdf)
- [S0126 - ComRAT](../../../Threat%20Intelligence/Software/Malware/S0126%20-%20ComRAT.md) — [ComRAT](https://attack.mitre.org/software/S0126) has been programmed to sleep outside local business hours (9 to 5, Monday to Friday).(Citation: ESET ComRAT May 2020) [ESET ComRAT May 2020](https://www.welivesecurity.com/wp-content/uploads/2020/05/ESET_Turla_ComRAT.pdf)
- [S0200 - Dipsind](../../../Threat%20Intelligence/Software/Malware/S0200%20-%20Dipsind.md) — [Dipsind](https://attack.mitre.org/software/S0200) can be configured to only run during normal working hours, which would make its communications harder to distinguish from normal traffic.(Citation: Microsoft PLATINUM April 2016) [Microsoft PLATINUM April 2016](https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf)
- [S0696 - Flagpro](../../../Threat%20Intelligence/Software/Malware/S0696%20-%20Flagpro.md) — [Flagpro](https://attack.mitre.org/software/S0696) has the ability to wait for a specified time interval between communicating with and executing commands from C2.(Citation: NTT Security Flagpro new December 2021) [NTT Security Flagpro new December 2021](https://insight-jp.nttsecurity.com/post/102hf3q/flagpro-the-new-malware-used-by-blacktech)
- [G0126 - Higaisa](../../../Threat%20Intelligence/Groups/G0126%20-%20Higaisa.md) — [Higaisa](https://attack.mitre.org/groups/G0126) sent the victim computer identifier in a User-Agent string back to the C2 server every 10 minutes.(Citation: PTSecurity Higaisa 2020) [PTSecurity Higaisa 2020](https://www.ptsecurity.com/ww-en/analytics/pt-esc-threat-intelligence/covid-19-and-new-year-greetings-the-higaisa-group/)
- [S0283 - jRAT](../../../Threat%20Intelligence/Software/Malware/S0283%20-%20jRAT.md) — [jRAT](https://attack.mitre.org/software/S0283) can be configured to reconnect at certain intervals.(Citation: Kaspersky Adwind Feb 2016) [Kaspersky Adwind Feb 2016](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07195002/KL_AdwindPublicReport_2016.pdf)
- [S0265 - Kazuar](../../../Threat%20Intelligence/Software/Malware/S0265%20-%20Kazuar.md) — [Kazuar](https://attack.mitre.org/software/S0265) can sleep for a specific time and be set to communicate at specific intervals.(Citation: Unit 42 Kazuar May 2017) [Unit 42 Kazuar May 2017](https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/)
- [S0395 - LightNeuron](../../../Threat%20Intelligence/Software/Malware/S0395%20-%20LightNeuron.md) — [LightNeuron](https://attack.mitre.org/software/S0395) can be configured to exfiltrate data during nighttime or working hours.(Citation: ESET LightNeuron May 2019) [ESET LightNeuron May 2019](https://www.welivesecurity.com/wp-content/uploads/2019/05/ESET-LightNeuron.pdf)
- [S0211 - Linfo](../../../Threat%20Intelligence/Software/Malware/S0211%20-%20Linfo.md) — [Linfo](https://attack.mitre.org/software/S0211) creates a backdoor through which remote attackers can change the frequency at which compromised hosts contact remote C2 infrastructure.(Citation: Symantec Linfo May 2012) [Symantec Linfo May 2012](https://www.symantec.com/security_response/writeup.jsp?docid=2012-051605-2535-99)
- [S0409 - Machete](../../../Threat%20Intelligence/Software/Malware/S0409%20-%20Machete.md) — [Machete](https://attack.mitre.org/software/S0409) sends stolen data to the C2 server every 10 minutes.(Citation: ESET Machete July 2019) [ESET Machete July 2019](https://www.welivesecurity.com/wp-content/uploads/2019/08/ESET_Machete.pdf)
- [S1100 - Ninja](../../../Threat%20Intelligence/Software/Malware/S1100%20-%20Ninja.md) — [Ninja](https://attack.mitre.org/software/S1100) can configure its agent to work only in specific time frames.(Citation: Kaspersky ToddyCat June 2022) [Kaspersky ToddyCat June 2022](https://securelist.com/toddycat/106799/)
- [S0223 - POWERSTATS](../../../Threat%20Intelligence/Software/Malware/S0223%20-%20POWERSTATS.md) — [POWERSTATS](https://attack.mitre.org/software/S0223) can sleep for a given number of seconds.(Citation: FireEye MuddyWater Mar 2018) [FireEye MuddyWater Mar 2018](https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html)
- [S0596 - ShadowPad](../../../Threat%20Intelligence/Software/Malware/S0596%20-%20ShadowPad.md) — [ShadowPad](https://attack.mitre.org/software/S0596) has sent data back to C2 every 8 hours.(Citation: Securelist ShadowPad Aug 2017) [Securelist ShadowPad Aug 2017](https://securelist.com/shadowpad-in-corporate-networks/81432/)
- [S1019 - Shark](../../../Threat%20Intelligence/Software/Malware/S1019%20-%20Shark.md) — [Shark](https://attack.mitre.org/software/S1019) can pause C2 communications for a specified time.(Citation: ClearSky Siamesekitten August 2021) [ClearSky Siamesekitten August 2021](https://www.clearskysec.com/siamesekitten/)
- [S0444 - ShimRat](../../../Threat%20Intelligence/Software/Malware/S0444%20-%20ShimRat.md) — [ShimRat](https://attack.mitre.org/software/S0444) can sleep when instructed to do so by the C2.(Citation: FOX-IT May 2016 Mofang) [FOX-IT May 2016 Mofang](https://foxitsecurity.files.wordpress.com/2016/06/fox-it_mofang_threatreport_tlp-white.pdf)
- [S0668 - TinyTurla](../../../Threat%20Intelligence/Software/Malware/S0668%20-%20TinyTurla.md) — [TinyTurla](https://attack.mitre.org/software/S0668) contacts its C2 based on a scheduled timing set in its configuration.(Citation: Talos TinyTurla September 2021) [Talos TinyTurla September 2021](https://blog.talosintelligence.com/2021/09/tinyturla.html)

## Detection strategies

- [DET0399 - Detection Strategy for Scheduled Transfer and Recurrent Exfiltration Patterns](../../../Defenses/Detection%20Strategies/DET0399%20-%20Detection%20Strategy%20for%20Scheduled%20Transfer%20and%20Recurrent%20Exfiltration%20Patterns.md)

## Mitigations

- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary command and control infrastructure and malware can be used to mitigate activity at the network level. Signatures are often for unique indicators within protocols and may be based on the specific obfuscation technique used by a particular adversary or tool, and will likely be different across various malware families and versions. Adversaries will likely change tool command and control signatures over time or construct protocols in such a way to avoid detection by common defensive tools. (Citation: University of Birmingham C2) [University of Birmingham C2](https://arxiv.org/pdf/1408.1136)

## Sources

- [Delay Code Execution in Java](https://www.javathinking.com/blog/how-to-delay-code-execution-in-java/#google_vignette)
