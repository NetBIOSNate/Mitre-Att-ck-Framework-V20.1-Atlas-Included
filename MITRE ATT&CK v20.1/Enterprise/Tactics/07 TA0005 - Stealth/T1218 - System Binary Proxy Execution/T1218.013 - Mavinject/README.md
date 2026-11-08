# T1218.013 - Mavinject

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse mavinject.exe to proxy execution of malicious code. Mavinject.exe is the Microsoft Application Virtualization Injector, a Windows utility that can inject code into external processes as part of Microsoft Application Virtualization (App-V).(Citation: LOLBAS Mavinject)

Adversaries may abuse mavinject.exe to inject malicious DLLs into running processes (i.e. [Dynamic-link Library Injection](https://attack.mitre.org/techniques/T1055/001)), allowing for arbitrary code execution (ex. <code>C:\Windows\system32\mavinject.exe PID /INJECTRUNNING PATH_DLL</code>).(Citation: ATT Lazarus TTP Evolution)(Citation: Reaqta Mavinject) Since mavinject.exe may be digitally signed by Microsoft, proxying execution via this method may evade detection by security products because the execution is masked under a legitimate process. 

In addition to [Dynamic-link Library Injection](https://attack.mitre.org/techniques/T1055/001), Mavinject.exe can also be abused to perform import descriptor injection via its  <code>/HMODULE</code> command-line parameter (ex. <code>mavinject.exe PID /HMODULE=BASE_ADDRESS PATH_DLL ORDINAL_NUMBER</code>). This command would inject an import table entry consisting of the specified DLL into the module at the given base address.(Citation: Mavinject Functionality Deconstructed)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/013)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider removing mavinject.exe if Microsoft App-V is not used within a given environment.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control configured to block execution of mavinject.exe if it is not required for a given system or network to prevent potential misuse by adversaries.

## Procedure examples

- [S1239 - TONESHELL](../../../../Threat%20Intelligence/Software/Malware/S1239%20-%20TONESHELL.md) — [TONESHELL](https://attack.mitre.org/software/S1239) has injected its malicious payload into a running process through Windows utility Microsoft Application Virtualization Injector `MAVInject.exe`.(Citation: Trend Micro Mustang Panda Earth Preta Toneshell February 2025) [Trend Micro Mustang Panda Earth Preta Toneshell February 2025](https://www.trendmicro.com/en_us/research/25/b/earth-preta-mixes-legitimate-and-malicious-components-to-sidestep-detection.html)

## Detection strategies

- [DET0433 - Detecting Code Injection via mavinject.exe (App-V Injector)](../../../../Defenses/Detection%20Strategies/DET0433%20-%20Detecting%20Code%20Injection%20via%20mavinject.exe%20%28App-V%20Injector%29.md)

## Sources

- [ATT Lazarus TTP Evolution](https://cybersecurity.att.com/blogs/labs-research/lazarus-campaign-ttps-and-evolution)
- [LOLBAS Mavinject](https://lolbas-project.github.io/lolbas/Binaries/Mavinject/)
- [Mavinject Functionality Deconstructed](https://posts.specterops.io/mavinject-exe-functionality-deconstructed-c29ab2cf5c0e)
- [Reaqta Mavinject](https://reaqta.com/2017/12/mavinject-microsoft-injector/)
