# T1055.014 - VDSO Hijacking

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject malicious code into processes via VDSO hijacking in order to evade process-based defenses as well as possibly elevate privileges. Virtual dynamic shared object (vdso) hijacking is a method of executing arbitrary code in the address space of a separate live process. 

VDSO hijacking involves redirecting calls to dynamically linked shared libraries. Memory protections may prevent writing executable code to a process via [Ptrace System Calls](https://attack.mitre.org/techniques/T1055/008). However, an adversary may hijack the syscall interface code stubs mapped into a process from the vdso shared object to execute syscalls to open and map a malicious shared object. This code can then be invoked by redirecting the execution flow of the process via patched memory address references stored in a process' global offset table (which stores absolute addresses of mapped library functions).(Citation: ELF Injection May 2009)(Citation: Backtrace VDSO)(Citation: VDSO Aug 2005)(Citation: Syscall 2014)

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via VDSO hijacking may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/014)

**Tactics**  [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md), [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.

## Detection strategies

- [DET0448 - Detection Strategy for VDSO Hijacking on Linux](../../../../Defenses/Detection%20Strategies/DET0448%20-%20Detection%20Strategy%20for%20VDSO%20Hijacking%20on%20Linux.md)

## Sources

- [Backtrace VDSO](https://web.archive.org/web/20210205211142/https://backtrace.io/blog/backtrace/elf-shared-library-injection-forensics/)
- [Syscall 2014](https://lwn.net/Articles/604515/)
- [ELF Injection May 2009](https://web.archive.org/web/20150711051625/http://vxer.org/lib/vrn00.html)
- [VDSO Aug 2005](https://web.archive.org/web/20051013084246/http://www.trilithium.com/johan/2005/08/linux-gate/)
