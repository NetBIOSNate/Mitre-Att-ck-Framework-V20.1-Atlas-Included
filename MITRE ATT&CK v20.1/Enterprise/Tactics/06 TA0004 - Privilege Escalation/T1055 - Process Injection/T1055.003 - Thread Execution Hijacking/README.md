# T1055.003 - Thread Execution Hijacking

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject malicious code into hijacked processes in order to evade process-based defenses as well as possibly elevate privileges. Thread Execution Hijacking is a method of executing arbitrary code in the address space of a separate live process. 

Thread Execution Hijacking is commonly performed by suspending an existing process then unmapping/hollowing its memory, which can then be replaced with malicious code or the path to a DLL. A handle to an existing victim process is first created with native Windows API calls such as <code>OpenThread</code>. At this point the process can be suspended then written to, realigned to the injected code, and resumed via <code>SuspendThread </code>, <code>VirtualAllocEx</code>, <code>WriteProcessMemory</code>, <code>SetThreadContext</code>, then <code>ResumeThread</code> respectively.(Citation: Elastic Process Injection July 2017)

This is very similar to [Process Hollowing](https://attack.mitre.org/techniques/T1055/012) but targets an existing process rather than creating a process in a suspended state.  

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via Thread Execution Hijacking may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/003)

**Tactics**  [Privilege Escalation](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0168 - Gazer](../../../../Threat%20Intelligence/Software/Malware/S0168%20-%20Gazer.md) — [Gazer](https://attack.mitre.org/software/S0168) performs thread execution hijacking to inject its orchestrator into a running thread from a remote process.(Citation: ESET Gazer Aug 2017)(Citation: Securelist WhiteBear Aug 2017) [ESET Gazer Aug 2017](https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf) · [Securelist WhiteBear Aug 2017](https://securelist.com/introducing-whitebear/81638/)
- [S1145 - Pikabot](../../../../Threat%20Intelligence/Software/Malware/S1145%20-%20Pikabot.md) — [Pikabot](https://attack.mitre.org/software/S1145) can create a suspended instance of a legitimate process (e.g., ctfmon.exe), allocate memory within the suspended process corresponding to [Pikabot](https://attack.mitre.org/software/S1145)'s core module, then redirect execution flow via `SetContextThread` API so that when the thread resumes the [Pikabot](https://attack.mitre.org/software/S1145) core module is executed.(Citation: Elastic Pikabot 2024) [Elastic Pikabot 2024](https://www.elastic.co/security-labs/pikabot-i-choose-you)
- [S0094 - Trojan.Karagany](../../../../Threat%20Intelligence/Software/Malware/S0094%20-%20Trojan.Karagany.md) — [Trojan.Karagany](https://attack.mitre.org/software/S0094) can inject a suspended thread of its own process into a new process and initiate via the <code>ResumeThread</code> API.(Citation: Secureworks Karagany July 2019) [Secureworks Karagany July 2019](https://www.secureworks.com/research/updated-karagany-malware-targets-energy-sector)
- [S9050 - Vidar](../../../../Threat%20Intelligence/Software/Malware/S9050%20-%20Vidar.md) — [Vidar](https://attack.mitre.org/software/S9050) has injected code into the suspended RegAsm.exe process.(Citation: Cyfirma_Vidar_June2024) [Cyfirma_Vidar_June2024](https://www.cyfirma.com/research/vidar-stealer-an-in-depth-analysis-of-an-information-stealing-malware/)
- [S0579 - Waterbear](../../../../Threat%20Intelligence/Software/Malware/S0579%20-%20Waterbear.md) — [Waterbear](https://attack.mitre.org/software/S0579) can use thread injection to inject shellcode into the process of security software.(Citation: Trend Micro Waterbear December 2019) [Trend Micro Waterbear December 2019](https://www.trendmicro.com/en_us/research/19/l/waterbear-is-back-uses-api-hooking-to-evade-security-product-detection.html)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.

## Detection strategies

- [DET0295 - Behavioral Detection of Thread Execution Hijacking via Thread Suspension and Context Switching](../../../../Defenses/Detection%20Strategies/DET0295%20-%20Behavioral%20Detection%20of%20Thread%20Execution%20Hijacking%20via%20Thread%20Suspension%20and%20Context.md)

## Sources

- [Elastic Process Injection July 2017](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
