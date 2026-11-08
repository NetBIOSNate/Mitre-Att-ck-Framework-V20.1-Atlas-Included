# T1056.004 - Credential API Hooking

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1056 - Input Capture](../README.md)

Adversaries may hook into Windows application programming interface (API) functions and Linux system functions to collect user credentials. Malicious hooking mechanisms may capture API or function calls that include parameters that reveal user authentication credentials.(Citation: Microsoft TrojanSpy:Win32/Ursnif.gen!I Sept 2017) Unlike [Keylogging](https://attack.mitre.org/techniques/T1056/001), this technique focuses specifically on API functions that include parameters that reveal user credentials. 

In Windows, hooking involves redirecting calls to these functions and can be implemented via:

* **Hooks procedures**, which intercept and execute designated code in response to events such as messages, keystrokes, and mouse inputs.(Citation: Microsoft Hook Overview)(Citation: Elastic Process Injection July 2017)
* **Import address table (IAT) hooking**, which use modifications to a process’s IAT, where pointers to imported API functions are stored.(Citation: Elastic Process Injection July 2017)(Citation: Adlice Software IAT Hooks Oct 2014)(Citation: MWRInfoSecurity Dynamic Hooking 2015)
* **Inline hooking**, which overwrites the first bytes in an API function to redirect code flow.(Citation: Elastic Process Injection July 2017)(Citation: HighTech Bridge Inline Hooking Sept 2011)(Citation: MWRInfoSecurity Dynamic Hooking 2015)

In Linux and macOS, adversaries may hook into system functions via the `LD_PRELOAD` (Linux) or `DYLD_INSERT_LIBRARIES` (macOS) environment variables, which enables loading shared libraries into a program’s address space. For example, an adversary may capture credentials by hooking into the `libc read` function leveraged by SSH or SCP.(Citation: Intezer Symbiote 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1056/004)

**Tactics**  [Credential Access](../../README.md), [Collection](../../../12%20TA0009%20-%20Collection/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0484 - Carberp](../../../../Threat%20Intelligence/Software/Malware/S0484%20-%20Carberp.md) — [Carberp](https://attack.mitre.org/software/S0484) has hooked several Windows API functions to steal credentials.(Citation: Prevx Carberp March 2011) [Prevx Carberp March 2011](https://web.archive.org/web/20231227000328/http://pxnow.prevx.com/content/blog/carberp-a_modular_information_stealing_trojan.pdf)
- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) contains some modules that leverage API hooking to carry out tasks, such as netripper.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [S0182 - FinFisher](../../../../Threat%20Intelligence/Software/Malware/S0182%20-%20FinFisher.md) — [FinFisher](https://attack.mitre.org/software/S0182) hooks processes by modifying IAT pointers to CreateWindowEx.(Citation: FinFisher Citation)(Citation: Elastic Process Injection July 2017) [FinFisher Citation](https://web.archive.org/web/20171222050934/http://www.finfisher.com/FinFisher/index.html) · [Elastic Process Injection July 2017](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
- [S0353 - NOKKI](../../../../Threat%20Intelligence/Software/Malware/S0353%20-%20NOKKI.md) — [NOKKI](https://attack.mitre.org/software/S0353) uses the Windows call SetWindowsHookEx and begins injecting it into every GUI process running on the victim's machine.(Citation: Unit 42 NOKKI Sept 2018) [Unit 42 NOKKI Sept 2018](https://researchcenter.paloaltonetworks.com/2018/09/unit42-new-konni-malware-attacking-eurasia-southeast-asia/)
- [G0068 - PLATINUM](../../../../Threat%20Intelligence/Groups/G0068%20-%20PLATINUM.md) — [PLATINUM](https://attack.mitre.org/groups/G0068) is capable of using Windows hook interfaces for information gathering such as credential access.(Citation: Microsoft PLATINUM April 2016) [Microsoft PLATINUM April 2016](https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf)
- [S0416 - RDFSNIFFER](../../../../Threat%20Intelligence/Software/Malware/S0416%20-%20RDFSNIFFER.md) — [RDFSNIFFER](https://attack.mitre.org/software/S0416) hooks several Win32 API functions to hijack elements of the remote system management user-interface.(Citation: FireEye FIN7 Oct 2019) [FireEye FIN7 Oct 2019](https://www.fireeye.com/blog/threat-research/2019/10/mahalo-fin7-responding-to-new-tools-and-techniques.html)
- [S0266 - TrickBot](../../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) has the ability to capture RDP credentials by capturing the <code>CredEnumerateA</code> API(Citation: TrendMicro Trickbot Feb 2019) [TrendMicro Trickbot Feb 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/trickbot-adds-remote-application-credential-grabbing-capabilities-to-its-repertoire/)
- [S0386 - Ursnif](../../../../Threat%20Intelligence/Software/Malware/S0386%20-%20Ursnif.md) — [Ursnif](https://attack.mitre.org/software/S0386) has hooked APIs to perform a wide variety of information theft, such as monitoring traffic from browsers.(Citation: TrendMicro Ursnif Mar 2015) [TrendMicro Ursnif Mar 2015](https://web.archive.org/web/20210719165945/https://www.trendmicro.com/en_us/research/15/c/ursnif-the-multifaceted-malware.html?_ga=2.165628854.808042651.1508120821-744063452.1505819992)
- [S1154 - VersaMem](../../../../Threat%20Intelligence/Software/Malware/S1154%20-%20VersaMem.md) — [VersaMem](https://attack.mitre.org/software/S1154) hooked and overrided Versa's built-in authentication method, `setUserPassword`, to intercept plaintext credentials when submitted to the server.(Citation: Lumen Versa 2024) [Lumen Versa 2024](https://www.lumen.com/blog/en-us/uncovering-versa-director-zero-day-exploitation)
- [S0251 - Zebrocy](../../../../Threat%20Intelligence/Software/Malware/S0251%20-%20Zebrocy.md) — [Zebrocy](https://attack.mitre.org/software/S0251) installs an application-defined Windows hook to get notified when a network drive has been attached, so it can then use the hook to call its RecordToFile file stealing method.(Citation: Securelist Sofacy Feb 2018) [Securelist Sofacy Feb 2018](https://securelist.com/a-slice-of-2017-sofacy-activity/83930/)
- [S0330 - Zeus Panda](../../../../Threat%20Intelligence/Software/Malware/S0330%20-%20Zeus%20Panda.md) — [Zeus Panda](https://attack.mitre.org/software/S0330) hooks processes by leveraging its own IAT hooked functions.(Citation: GDATA Zeus Panda June 2017) [GDATA Zeus Panda June 2017](https://cyberwtf.files.wordpress.com/2017/07/panda-whitepaper.pdf)
- [S0412 - ZxShell](../../../../Threat%20Intelligence/Software/Malware/S0412%20-%20ZxShell.md) — [ZxShell](https://attack.mitre.org/software/S0412) hooks several API functions to spawn system threads.(Citation: Talos ZxShell Oct 2014) [Talos ZxShell Oct 2014](https://blogs.cisco.com/security/talos/opening-zxshell)

## Detection strategies

- [DET0139 - Detection of Credential Harvesting via API Hooking](../../../../Defenses/Detection%20Strategies/DET0139%20-%20Detection%20of%20Credential%20Harvesting%20via%20API%20Hooking.md)

## Sources

- [EyeofRa Detecting Hooking June 2017](https://eyeofrablog.wordpress.com/2017/06/27/windows-keylogger-part-2-defense-against-user-land/)
- [Zairon Hooking Dec 2006](https://zairon.wordpress.com/2006/12/06/any-application-defined-hook-procedure-on-my-machine/)
- [GMER Rootkits](http://www.gmer.net/)
- [MWRInfoSecurity Dynamic Hooking 2015](https://www.mwrinfosecurity.com/our-thinking/dynamic-hooking-techniques-user-mode/)
- [Elastic Process Injection July 2017](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
- [Intezer Symbiote 2022](https://intezer.com/blog/research/new-linux-threat-symbiote/)
- [HighTech Bridge Inline Hooking Sept 2011](https://www.scribd.com/document/68671361/Inline-Hooking-in-Windows)
- [Microsoft TrojanSpy:Win32/Ursnif.gen!I Sept 2017](https://www.microsoft.com/en-us/wdsi/threats/malware-encyclopedia-description?Name=TrojanSpy:Win32/Ursnif.gen!I&threatId=-2147336918)
- [Microsoft Hook Overview](https://msdn.microsoft.com/library/windows/desktop/ms644959.aspx)
- [Microsoft Process Snapshot](https://msdn.microsoft.com/library/windows/desktop/ms686701.aspx)
- [PreKageo Winhook Jul 2011](https://github.com/prekageo/winhook)
- [Jay GetHooks Sept 2011](https://github.com/jay/gethooks)
- [StackExchange Hooks Jul 2012](https://security.stackexchange.com/questions/17904/what-are-the-methods-to-find-hooked-functions-and-apis)
- [Adlice Software IAT Hooks Oct 2014](https://www.adlice.com/userland-rootkits-part-1-iat-hooks/)
- [Volatility Detecting Hooks Sept 2012](https://volatility-labs.blogspot.com/2012/09/movp-31-detecting-malware-hooks-in.html)
