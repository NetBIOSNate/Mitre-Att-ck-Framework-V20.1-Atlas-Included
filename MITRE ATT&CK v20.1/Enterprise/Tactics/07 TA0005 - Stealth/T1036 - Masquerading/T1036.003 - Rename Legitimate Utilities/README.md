# T1036.003 - Rename Legitimate Utilities

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

Adversaries may rename legitimate / system utilities to try to evade security mechanisms concerning the usage of those utilities. Security monitoring and control mechanisms may be in place for legitimate utilities adversaries are capable of abusing, including both built-in binaries and tools such as PSExec, AutoHotKey, and IronPython.(Citation: LOLBAS Main Site)(Citation: Huntress Python Malware 2025)(Citation: The DFIR Report AutoHotKey 2023)(Citation: Splunk Detect Renamed PSExec) It may be possible to bypass those security mechanisms by renaming the utility prior to utilization (ex: rename <code>rundll32.exe</code>).(Citation: Elastic Masquerade Ball) An alternative case occurs when a legitimate utility is copied or moved to a different directory and renamed to avoid detections based on these utilities executing from non-standard paths.(Citation: F-Secure CozyDuke)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/003)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0005 - Renamed Legitimate Utility Execution with Metadata Mismatch and Suspicious Path](../../../../Defenses/Detection%20Strategies/DET0005%20-%20Renamed%20Legitimate%20Utility%20Execution%20with%20Metadata%20Mismatch%20and%20Suspicious%20Path.md)

## Procedure examples

- [G0050 - APT32](../../../../Threat%20Intelligence/Groups/G0050%20-%20APT32.md) — [APT32](https://attack.mitre.org/groups/G0050) has moved and renamed pubprn.vbs to a .txt file to avoid detection.(Citation: Twitter ItsReallyNick APT32 pubprn Masquerade) [Twitter ItsReallyNick APT32 pubprn Masquerade](https://x.com/ItsReallyNick/status/945681177108762624)
- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has renamed system utilities, such as `rundll32.exe` and `mshta.exe`, to avoid detection.(Citation: 1 - appv) [1 - appv](https://securelist.com/bluenoroff-methods-bypass-motw/108383/)
- [S0046 - CozyCar](../../../../Threat%20Intelligence/Software/Malware/S0046%20-%20CozyCar.md) — The [CozyCar](https://attack.mitre.org/software/S0046) dropper has masqueraded a copy of the infected system's rundll32.exe executable that was moved to the malware's install directory and renamed according to a predefined configuration file.(Citation: F-Secure CozyDuke) [F-Secure CozyDuke](https://www.f-secure.com/documents/996508/1030745/CozyDuke)
- [G1034 - Daggerfly](../../../../Threat%20Intelligence/Groups/G1034%20-%20Daggerfly.md) — [Daggerfly](https://attack.mitre.org/groups/G1034) used a renamed version of rundll32.exe, such as "dbengin.exe" located in the `ProgramData\Microsoft\PlayReady` directory, to proxy malicious DLL execution.(Citation: Symantec Daggerfly 2023) [Symantec Daggerfly 2023](https://symantec-enterprise-blogs.security.com/threat-intelligence/apt-attacks-telecoms-africa-mgbot)
- [S1111 - DarkGate](../../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) executes a Windows Batch script during installation that creases a randomly-named directory in the <code>C:\\</code> root directory that copies and renames the legitimate Windows <curl>curl</code> command to this new location.(Citation: Trellix Darkgate 2023) [Trellix Darkgate 2023](https://www.trellix.com/blogs/research/the-continued-evolution-of-the-darkgate-malware-as-a-service/)
- [G0093 - GALLIUM](../../../../Threat%20Intelligence/Groups/G0093%20-%20GALLIUM.md) — [GALLIUM](https://attack.mitre.org/groups/G0093) used a renamed cmd.exe file to evade detection.(Citation: Cybereason Soft Cell June 2019) [Cybereason Soft Cell June 2019](https://www.cybereason.com/blog/operation-soft-cell-a-worldwide-campaign-against-telecommunications-providers)
- [S1020 - Kevin](../../../../Threat%20Intelligence/Software/Malware/S1020%20-%20Kevin.md) — [Kevin](https://attack.mitre.org/software/S1020) has renamed an image of `cmd.exe` with a random name followed by a `.tmpl` extension.(Citation: Kaspersky Lyceum October 2021) [Kaspersky Lyceum October 2021](https://vblocalhost.com/uploads/VB2021-Kayal-etal.pdf)
- [G0032 - Lazarus Group](../../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) has renamed system utilities such as <code>wscript.exe</code> and <code>mshta.exe</code>.(Citation: Qualys LolZarus) [Qualys LolZarus](https://blog.qualys.com/vulnerabilities-threat-research/2022/02/08/lolzarus-lazarus-group-incorporating-lolbins-into-campaigns)
- [G0045 - menuPass](../../../../Threat%20Intelligence/Groups/G0045%20-%20menuPass.md) — [menuPass](https://attack.mitre.org/groups/G0045) has renamed [certutil](https://attack.mitre.org/software/S0160) and moved it to a different location on the system to avoid detection based on use of the tool.(Citation: FireEye APT10 Sept 2018) [FireEye APT10 Sept 2018](https://www.fireeye.com/blog/threat-research/2018/09/apt10-targeting-japanese-corporations-using-updated-ttps.html)
- [S9014 - PHASEJAM](../../../../Threat%20Intelligence/Software/Malware/S9014%20-%20PHASEJAM.md) — [PHASEJAM](https://attack.mitre.org/software/S9014) has renamed the file `/home/bin/remotedebug` to `remotedebug.bak`, allowing the threats actors to write a malicious `/home/bin/remotedebug` shell script.(Citation: Google UNC5221 Ivanti January 2025) [Google UNC5221 Ivanti January 2025](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day)
- [S1183 - StrelaStealer](../../../../Threat%20Intelligence/Software/Malware/S1183%20-%20StrelaStealer.md) — [StrelaStealer](https://attack.mitre.org/software/S1183) has used a renamed, legitimate `msinfo32.exe` executable to sideload the [StrelaStealer](https://attack.mitre.org/software/S1183) payload during initial installation.(Citation: DCSO StrelaStealer 2022) [DCSO StrelaStealer 2022](https://medium.com/@DCSO_CyTec/shortandmalicious-strelastealer-aims-for-mail-credentials-a4c3e78c8abc)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Use file system access controls to protect folders such as `C:\Windows\System32`.

## Sources

- [Elastic Masquerade Ball](https://www.elastic.co/blog/how-hunt-masquerade-ball)
- [F-Secure CozyDuke](https://www.f-secure.com/documents/996508/1030745/CozyDuke)
- [LOLBAS Main Site](https://lolbas-project.github.io/)
- [Huntress Python Malware 2025](https://www.huntress.com/blog/snakes-on-a-domain-an-analysis-of-a-python-malware-loader)
- [Splunk Detect Renamed PSExec](https://research.splunk.com/endpoint/683e6196-b8e8-11eb-9a79-acde48001122/)
- [The DFIR Report AutoHotKey 2023](https://thedfirreport.com/2023/02/06/collect-exfiltrate-sleep-repeat/)
