# T1055.011 - Extra Window Memory Injection

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject malicious code into a process via Extra Window Memory (EWM) in order to evade process-based defenses as well as possibly elevate privileges. EWM injection is a method of executing arbitrary code in the address space of a separate live process. 

Before creating a window, graphical Windows-based processes must register a windows class, which stipulates appearance and behavior (via windows procedures, which are functions that handle input/output of data).(Citation: Microsoft Window Classes) Registration of new windows classes can include a request for up to 40 bytes of EWM to be appended to the allocated memory of each instance of that class. This EWM is intended to store data specific to that window and has specific application programming interface (API) functions to set and get its value.(Citation: Microsoft GetWindowLong function)(Citation: Microsoft SetWindowLong function)

Although small, the EWM is large enough to store a 32-bit pointer and is often used to point to a windows procedure. Malware may possibly utilize this memory location in part of an attack chain that includes writing code to shared sections of the process’s memory, placing a pointer to the code in EWM, then invoking execution by returning execution control to the address in the process’s EWM.

Execution granted through EWM injection may allow access to both the target process's memory and possibly elevated privileges. Writing payloads to shared sections also avoids the use of highly monitored API calls such as <code>WriteProcessMemory</code> and <code>CreateRemoteThread</code>.(Citation: Elastic Process Injection July 2017) More sophisticated malware samples may also potentially bypass protection mechanisms such as data execution prevention (DEP) by triggering a combination of windows procedures and other system functions that will rewrite the malicious payload inside an executable portion of the target process.(Citation: MalwareTech Power Loader Aug 2013)(Citation: WeLiveSecurity Gapz and Redyms Mar 2013)

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via EWM injection may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/011)

**Tactics**  [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0217 - Detection Strategy for Extra Window Memory (EWM) Injection on Windows](../../../../Defenses/Detection%20Strategies/DET0217%20-%20Detection%20Strategy%20for%20Extra%20Window%20Memory%20%28EWM%29%20Injection%20on%20Windows.md)

## Procedure examples

- [S0091 - Epic](../../../../Threat%20Intelligence/Software/Malware/S0091%20-%20Epic.md) — [Epic](https://attack.mitre.org/software/S0091) has overwritten the function pointer in the extra window memory of Explorer's Shell_TrayWnd in order to execute malicious code in the context of the explorer.exe process.(Citation: ESET Recon Snake Nest) [ESET Recon Snake Nest](https://recon.cx/2018/brussels/resources/slides/RECON-BRX-2018-Visiting-The-Snake-Nest.pdf)
- [S0177 - Power Loader](../../../../Threat%20Intelligence/Software/Malware/S0177%20-%20Power%20Loader.md) — [Power Loader](https://attack.mitre.org/software/S0177) overwrites Explorer’s Shell_TrayWnd extra window memory to redirect execution to a NTDLL function that is abused to assemble and execute a return-oriented programming (ROP) chain and create a malicious thread within Explorer.exe.(Citation: MalwareTech Power Loader Aug 2013)(Citation: WeLiveSecurity Gapz and Redyms Mar 2013) [MalwareTech Power Loader Aug 2013](https://www.malwaretech.com/2013/08/powerloader-injection-something-truly.html) · [WeLiveSecurity Gapz and Redyms Mar 2013](https://www.welivesecurity.com/2013/03/19/gapz-and-redyms-droppers-based-on-power-loader-code/)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.

## Sources

- [Elastic Process Injection July 2017](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
- [MalwareTech Power Loader Aug 2013](https://www.malwaretech.com/2013/08/powerloader-injection-something-truly.html)
- [WeLiveSecurity Gapz and Redyms Mar 2013](https://www.welivesecurity.com/2013/03/19/gapz-and-redyms-droppers-based-on-power-loader-code/)
- [Microsoft Window Classes](https://msdn.microsoft.com/library/windows/desktop/ms633574.aspx)
- [Microsoft GetWindowLong function](https://msdn.microsoft.com/library/windows/desktop/ms633584.aspx)
- [Microsoft SetWindowLong function](https://msdn.microsoft.com/library/windows/desktop/ms633591.aspx)
