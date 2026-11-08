# T1055.008 - Ptrace System Calls

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject malicious code into processes via ptrace (process trace) system calls in order to evade process-based defenses as well as possibly elevate privileges. Ptrace system call injection is a method of executing arbitrary code in the address space of a separate live process. 

Ptrace system call injection involves attaching to and modifying a running process. The ptrace system call enables a debugging process to observe and control another process (and each individual thread), including changing memory and register values.(Citation: PTRACE man) Ptrace system call injection is commonly performed by writing arbitrary code into a running process (ex: <code>malloc</code>) then invoking that memory with <code>PTRACE_SETREGS</code> to set the register containing the next instruction to execute. Ptrace system call injection can also be done with <code>PTRACE_POKETEXT</code>/<code>PTRACE_POKEDATA</code>, which copy data to a specific address in the target processes’ memory (ex: the current address of the next instruction).(Citation: PTRACE man)(Citation: Medium Ptrace JUL 2018) 

Ptrace system call injection may not be possible targeting processes that are non-child processes and/or have higher-privileges.(Citation: BH Linux Inject) 

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via ptrace system call injection may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/008)

**Tactics**  [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md), [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Procedure examples

- [S1109 - PACEMAKER](../../../../Threat%20Intelligence/Software/Malware/S1109%20-%20PACEMAKER.md) — [PACEMAKER](https://attack.mitre.org/software/S1109) can use PTRACE to attach to a targeted process to read process memory.(Citation: Mandiant Pulse Secure Zero-Day April 2021) [Mandiant Pulse Secure Zero-Day April 2021](https://www.mandiant.com/resources/blog/suspected-apt-actors-leverage-bypass-techniques-pulse-secure-zero-day)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Utilize Yama (ex: /proc/sys/kernel/yama/ptrace_scope) to mitigate ptrace based process injection by restricting the use of ptrace to privileged users only. Other mitigation controls involve the deployment of security kernel modules that provide advanced access control and process restrictions such as SELinux, grsecurity, and AppArmor.

## Detection strategies

- [DET0203 - Detection Strategy for Ptrace-Based Process Injection on Linux](../../../../Defenses/Detection%20Strategies/DET0203%20-%20Detection%20Strategy%20for%20Ptrace-Based%20Process%20Injection%20on%20Linux.md)

## Sources

- [BH Linux Inject](https://github.com/gaffe23/linux-inject/blob/master/slides_BHArsenal2015.pdf)
- [Medium Ptrace JUL 2018](https://medium.com/@jain.sm/code-injection-in-running-process-using-ptrace-d3ea7191a4be)
- [PTRACE man](http://man7.org/linux/man-pages/man2/ptrace.2.html)
