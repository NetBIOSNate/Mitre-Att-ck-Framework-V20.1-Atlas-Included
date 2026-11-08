# T1055.005 - Thread Local Storage

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject malicious code into processes via thread local storage (TLS) callbacks in order to evade process-based defenses as well as possibly elevate privileges. TLS callback injection is a method of executing arbitrary code in the address space of a separate live process. 

TLS callback injection involves manipulating pointers inside a portable executable (PE) to redirect a process to malicious code before reaching the code's legitimate entry point. TLS callbacks are normally used by the OS to set up and/or clean up data used by threads. Manipulating TLS callbacks may be performed by allocating and writing to specific offsets within a process’ memory space using other [Process Injection](https://attack.mitre.org/techniques/T1055) techniques such as [Process Hollowing](https://attack.mitre.org/techniques/T1055/012).(Citation: FireEye TLS Nov 2017)

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via TLS callback injection may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/005)

**Tactics**  [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0467 - Detection Strategy for TLS Callback Injection via PE Memory Modification and Hollowing](../../../../Defenses/Detection%20Strategies/DET0467%20-%20Detection%20Strategy%20for%20TLS%20Callback%20Injection%20via%20PE%20Memory%20Modification%20and%20Hollowin.md)

## Procedure examples

- [S1237 - CANONSTAGER](../../../../Threat%20Intelligence/Software/Malware/S1237%20-%20CANONSTAGER.md) — [CANONSTAGER](https://attack.mitre.org/software/S1237) uses the Thread Local Storage (TLS) array data structure to store function addresses resolved by its custom API hashing algorithm. The function addresses are later called throughout the binary from offsets into the TLS array.(Citation: Google Threat Intelligence Group MUSTANG PANDA PLUGX August 2025) [Google Threat Intelligence Group MUSTANG PANDA PLUGX August 2025](https://cloud.google.com/blog/topics/threat-intelligence/prc-nexus-espionage-targets-diplomats)
- [S0386 - Ursnif](../../../../Threat%20Intelligence/Software/Malware/S0386%20-%20Ursnif.md) — [Ursnif](https://attack.mitre.org/software/S0386) has injected code into target processes via thread local storage callbacks.(Citation: TrendMicro Ursnif Mar 2015)(Citation: TrendMicro PE_URSNIF.A2)(Citation: FireEye Ursnif Nov 2017) [TrendMicro Ursnif Mar 2015](https://web.archive.org/web/20210719165945/https://www.trendmicro.com/en_us/research/15/c/ursnif-the-multifaceted-malware.html?_ga=2.165628854.808042651.1508120821-744063452.1505819992) · [TrendMicro PE_URSNIF.A2](https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/PE_URSNIF.A2?_ga=2.131425807.1462021705.1559742358-1202584019.1549394279) · [FireEye Ursnif Nov 2017](https://www.fireeye.com/blog/threat-research/2017/11/ursnif-variant-malicious-tls-callback-technique.html)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.

## Sources

- [FireEye TLS Nov 2017](https://www.fireeye.com/blog/threat-research/2017/11/ursnif-variant-malicious-tls-callback-technique.html)
