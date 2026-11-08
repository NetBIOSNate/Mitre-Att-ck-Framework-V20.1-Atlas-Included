# T1631.001 - Ptrace System Calls

[Mobile](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1631 - Process Injection](../README.md)

Adversaries may inject malicious code into processes via ptrace (process trace) system calls in order to evade process-based defenses as well as possibly elevate privileges. Ptrace system call injection is a method of executing arbitrary code in the address space of a separate live process.  

Ptrace system call injection involves attaching to and modifying a running process. The ptrace system call enables a debugging process to observe and control another process (and each individual thread), including changing memory and register values.(Citation: PTRACE man) Ptrace system call injection is commonly performed by writing arbitrary code into a running process (e.g., by using `malloc`) then invoking that memory with `PTRACE_SETREGS` to set the register containing the next instruction to execute. Ptrace system call injection can also be done with `PTRACE_POKETEXT`/`PTRACE_POKEDATA`, which copy data to a specific address in the target process's memory (e.g., the current address of the next instruction).(Citation: PTRACE man)(Citation: Medium Ptrace JUL 2018)  

Ptrace system call injection may not be possible when targeting processes with high-privileges, and on some systems those that are non-child processes.(Citation: BH Linux Inject)  

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via ptrace system call injection may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1631/001)

**Tactics**  [Privilege Escalation](../../README.md), [Defense Evasion](../../../05%20TA0030%20-%20Defense%20Evasion/README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S0463 - INSOMNIA](../../../../Threat%20Intelligence/Software/Malware/S0463%20-%20INSOMNIA.md) — [INSOMNIA](https://attack.mitre.org/software/S0463) grants itself permissions by injecting its hash into the kernel’s trust cache.(Citation: Google Project Zero Insomnia) [Google Project Zero Insomnia](https://googleprojectzero.blogspot.com/2019/08/implant-teardown.html)
- [S0424 - Triada](../../../../Threat%20Intelligence/Software/Malware/S0424%20-%20Triada.md) — [Triada](https://attack.mitre.org/software/S0424) injects code into the Zygote process to effectively include itself in all forked processes. Additionally, code is injected into the Android Play Store App, web browser applications, and the system UI application.(Citation: Google Triada June 2019)(Citation: Kaspersky Triada March 2016) [Google Triada June 2019](https://security.googleblog.com/2019/06/pha-family-highlights-triada.html) · [Kaspersky Triada March 2016](https://www.kaspersky.com/blog/triada-trojan/11481/)
- [S0494 - Zen](../../../../Threat%20Intelligence/Software/Malware/S0494%20-%20Zen.md) — [Zen](https://attack.mitre.org/software/S0494) can inject code into the Setup Wizard at runtime to extract CAPTCHA images. [Zen](https://attack.mitre.org/software/S0494) can inject code into the `libc` of running processes to infect them with the malware.(Citation: Google Security Zen) [Google Security Zen](https://security.googleblog.com/2019/01/pha-family-highlights-zen-and-its.html)

## Detection strategies

- [DET0622 - Detection of Ptrace System Calls](../../../../Defenses/Detection%20Strategies/DET0622%20-%20Detection%20of%20Ptrace%20System%20Calls.md)

## Sources

- [BH Linux Inject](https://github.com/gaffe23/linux-inject/blob/master/slides_BHArsenal2015.pdf)
- [Medium Ptrace JUL 2018](https://medium.com/@jain.sm/code-injection-in-running-process-using-ptrace-d3ea7191a4be)
- [PTRACE man](http://man7.org/linux/man-pages/man2/ptrace.2.html)
