# T1547.004 - Winlogon Helper DLL

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may abuse features of Winlogon to execute DLLs and/or executables when a user logs in. Winlogon.exe is a Windows component responsible for actions at logon/logoff as well as the secure attention sequence (SAS) triggered by Ctrl-Alt-Delete. Registry entries in <code>HKLM\Software[\\Wow6432Node\\]\Microsoft\Windows NT\CurrentVersion\Winlogon\</code> and <code>HKCU\Software\Microsoft\Windows NT\CurrentVersion\Winlogon\</code> are used to manage additional helper programs and functionalities that support Winlogon.(Citation: Cylance Reg Persistence Sept 2013) 

Malicious modifications to these Registry keys may cause Winlogon to load and execute malicious DLLs and/or executables. Specifically, the following subkeys have been known to be possibly vulnerable to abuse:(Citation: Cylance Reg Persistence Sept 2013)

* Winlogon\Notify - points to notification package DLLs that handle Winlogon events
* Winlogon\Userinit - points to userinit.exe, the user initialization program executed when a user logs on
* Winlogon\Shell - points to explorer.exe, the system shell executed when a user logs on

Adversaries may take advantage of these features to repeatedly execute malicious code and establish persistence.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/004)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0534 - Bazar](../../../../Threat%20Intelligence/Software/Malware/S0534%20-%20Bazar.md) — [Bazar](https://attack.mitre.org/software/S0534) can use Winlogon Helper DLL to establish persistence.(Citation: Zscaler Bazar September 2020) [Zscaler Bazar September 2020](https://www.zscaler.com/blogs/research/spear-phishing-campaign-delivers-buer-and-bazar-malware)
- [S0351 - Cannon](../../../../Threat%20Intelligence/Software/Malware/S0351%20-%20Cannon.md) — [Cannon](https://attack.mitre.org/software/S0351) adds the Registry key <code>HKCU\Software\Microsoft\Windows NT\CurrentVersion\Winlogon</code> to establish persistence.(Citation: Unit42 Cannon Nov 2018) [Unit42 Cannon Nov 2018](https://researchcenter.paloaltonetworks.com/2018/11/unit42-sofacy-continues-global-attacks-wheels-new-cannon-trojan/)
- [S1066 - DarkTortilla](../../../../Threat%20Intelligence/Software/Malware/S1066%20-%20DarkTortilla.md) — [DarkTortilla](https://attack.mitre.org/software/S1066) has established persistence via the `Software\Microsoft\Windows NT\CurrentVersion\Winlogon` registry key.(Citation: Secureworks DarkTortilla Aug 2022) [Secureworks DarkTortilla Aug 2022](https://www.secureworks.com/research/darktortilla-malware-analysis)
- [S0200 - Dipsind](../../../../Threat%20Intelligence/Software/Malware/S0200%20-%20Dipsind.md) — A [Dipsind](https://attack.mitre.org/software/S0200) variant registers as a Winlogon Event Notify DLL to establish persistence.(Citation: Microsoft PLATINUM April 2016) [Microsoft PLATINUM April 2016](https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf)
- [S0168 - Gazer](../../../../Threat%20Intelligence/Software/Malware/S0168%20-%20Gazer.md) — [Gazer](https://attack.mitre.org/software/S0168) can establish persistence by setting the value “Shell” with “explorer.exe, %malware_pathfile%” under the Registry key <code>HKCU\Software\Microsoft\Windows NT\CurrentVersion\Winlogon</code>.(Citation: ESET Gazer Aug 2017) [ESET Gazer Aug 2017](https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf)
- [S0387 - KeyBoy](../../../../Threat%20Intelligence/Software/Malware/S0387%20-%20KeyBoy.md) — [KeyBoy](https://attack.mitre.org/software/S0387) issues the command <code>reg add “HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon”</code> to achieve persistence.(Citation: PWC KeyBoys Feb 2017) (Citation: CitizenLab KeyBoy Nov 2016) [CitizenLab KeyBoy Nov 2016](https://citizenlab.ca/2016/11/parliament-keyboy/) · [PWC KeyBoys Feb 2017](https://web.archive.org/web/20211129064701/https://www.pwc.co.uk/issues/cyber-security-services/research/the-keyboys-are-back-in-town.html)
- [S1202 - LockBit 3.0](../../../../Threat%20Intelligence/Software/Malware/S1202%20-%20LockBit%203.0.md) — [LockBit 3.0](https://attack.mitre.org/software/S1202) can enable automatic logon through the `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon` Registry key.(Citation: Joint Cybersecurity Advisory LockBit 3.0 MAR 2023) [Joint Cybersecurity Advisory LockBit 3.0 MAR 2023](https://www.cisa.gov/sites/default/files/2023-03/aa23-075a-stop-ransomware-lockbit.pdf)
- [S1242 - Qilin](../../../../Threat%20Intelligence/Software/Malware/S1242%20-%20Qilin.md) — [Qilin](https://attack.mitre.org/software/S1242) can configure a Winlogon registry entry.(Citation: Trend Micro Agenda Ransomware AUG 2022) [Trend Micro Agenda Ransomware AUG 2022](https://www.trendmicro.com/en_us/research/22/h/new-golang-ransomware-agenda-customizes-attacks.html)
- [S0375 - Remexi](../../../../Threat%20Intelligence/Software/Malware/S0375%20-%20Remexi.md) — [Remexi](https://attack.mitre.org/software/S0375) achieves persistence using Userinit by adding the Registry key <code>HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon\Userinit</code>.(Citation: Securelist Remexi Jan 2019) [Securelist Remexi Jan 2019](https://securelist.com/chafer-used-remexi-malware/89538/)
- [S0379 - Revenge RAT](../../../../Threat%20Intelligence/Software/Malware/S0379%20-%20Revenge%20RAT.md) — [Revenge RAT](https://attack.mitre.org/software/S0379) creates a Registry key at <code>HKCU\Software\Microsoft\Windows NT\CurrentVersion\Winlogon\Shell</code> to survive a system reboot.(Citation: Cylance Shaheen Nov 2018) [Cylance Shaheen Nov 2018](https://www.cylance.com/content/dam/cylance-web/en-us/resources/knowledge-center/resource-library/reports/WhiteCompanyOperationShaheenReport.pdf?_ga=2.161661948.1943296560.1555683782-1066572390.1555511517)
- [G0081 - Tropic Trooper](../../../../Threat%20Intelligence/Groups/G0081%20-%20Tropic%20Trooper.md) — [Tropic Trooper](https://attack.mitre.org/groups/G0081) has created the Registry key <code>HKCU\Software\Microsoft\Windows NT\CurrentVersion\Winlogon\Shell</code> and sets the value to establish persistence.(Citation: Unit 42 Tropic Trooper Nov 2016)(Citation: TrendMicro Tropic Trooper May 2020) [Unit 42 Tropic Trooper Nov 2016](https://researchcenter.paloaltonetworks.com/2016/11/unit42-tropic-trooper-targets-taiwanese-government-and-fossil-fuel-provider-with-poison-ivy/) · [TrendMicro Tropic Trooper May 2020](https://documents.trendmicro.com/assets/Tech-Brief-Tropic-Trooper-s-Back-USBferry-Attack-Targets-Air-gapped-Environments.pdf)
- [G0010 - Turla](../../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) established persistence by adding a Shell value under the Registry key <code>HKCU\Software\Microsoft\Windows NT\CurrentVersion\Winlogon</code>.(Citation: ESET Turla Mosquito Jan 2018) [ESET Turla Mosquito Jan 2018](https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf)
- [G0102 - Wizard Spider](../../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has established persistence using Userinit by adding the Registry key HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon.(Citation: FireEye KEGTAP SINGLEMALT October 2020) [FireEye KEGTAP SINGLEMALT October 2020](https://www.fireeye.com/blog/threat-research/2020/10/kegtap-and-singlemalt-with-a-ransomware-chaser.html)

## Detection strategies

- [DET0404 - Detect Winlogon Helper DLL Abuse via Registry and Process Artifacts on Windows](../../../../Defenses/Detection%20Strategies/DET0404%20-%20Detect%20Winlogon%20Helper%20DLL%20Abuse%20via%20Registry%20and%20Process%20Artifacts%20on%20Windows.md)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Identify and block potentially malicious software that may be executed through the Winlogon helper process by using application control (Citation: Beechey 2010) tools like AppLocker (Citation: Windows Commands JPCERT) (Citation: NSA MS AppLocker) that are capable of auditing and/or blocking unknown DLLs. [Beechey 2010](http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599) · [Windows Commands JPCERT](https://blogs.jpcert.or.jp/en/2016/01/windows-commands-abused-by-attackers.html) · [NSA MS AppLocker](https://apps.nsa.gov/iaarchive/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit the privileges of user accounts so that only authorized administrators can perform Winlogon helper changes.

## Sources

- [Cylance Reg Persistence Sept 2013](https://web.archive.org/web/20160214140250/http://blog.cylance.com/windows-registry-persistence-part-2-the-run-keys-and-search-order)
