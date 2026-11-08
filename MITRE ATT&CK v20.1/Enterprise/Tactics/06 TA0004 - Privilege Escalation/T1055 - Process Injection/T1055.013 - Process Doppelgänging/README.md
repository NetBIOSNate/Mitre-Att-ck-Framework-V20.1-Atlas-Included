# T1055.013 - Process Doppelgänging

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject malicious code into a process via process doppelgänging in order to evade process-based defenses as well as possibly elevate privileges. Process doppelgänging is a method of executing arbitrary code in the address space of a separate live process. 

Windows Transactional NTFS (TxF) was introduced in Vista as a method to perform safe file operations.(Citation: Microsoft TxF) To ensure data integrity, TxF enables only one transacted handle to write to a file at a given time. Until the write handle transaction is terminated, all other handles are isolated from the writer and may only read the committed version of the file that existed at the time the handle was opened.(Citation: Microsoft Basic TxF Concepts) To avoid corruption, TxF performs an automatic rollback if the system or application fails during a write transaction.(Citation: Microsoft Where to use TxF)

Although deprecated, the TxF application programming interface (API) is still enabled as of Windows 10.(Citation: BlackHat Process Doppelgänging Dec 2017)

Adversaries may abuse TxF to a perform a file-less variation of [Process Injection](https://attack.mitre.org/techniques/T1055). Similar to [Process Hollowing](https://attack.mitre.org/techniques/T1055/012), process doppelgänging involves replacing the memory of a legitimate process, enabling the veiled execution of malicious code that may evade defenses and detection. Process doppelgänging's use of TxF also avoids the use of highly-monitored API functions such as <code>NtUnmapViewOfSection</code>, <code>VirtualProtectEx</code>, and <code>SetThreadContext</code>.(Citation: BlackHat Process Doppelgänging Dec 2017)

Process Doppelgänging is implemented in 4 steps:

* Transact – Create a TxF transaction using a legitimate executable then overwrite the file with malicious code. These changes will be isolated and only visible within the context of the transaction.
* Load – Create a shared section of memory and load the malicious executable.
* Rollback – Undo changes to original executable, effectively removing malicious code from the file system.
* Animate – Create a process from the tainted section of memory and initiate execution.

This behavior will likely not result in elevated privileges since the injected process was spawned from (and thus inherits the security context) of the injecting process. However, execution via process doppelgänging may evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/013)

**Tactics**  [Privilege Escalation](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0534 - Bazar](../../../../Threat%20Intelligence/Software/Malware/S0534%20-%20Bazar.md) — [Bazar](https://attack.mitre.org/software/S0534) can inject into a target process using process doppelgänging.(Citation: Cybereason Bazar July 2020)(Citation: NCC Group Team9 June 2020) [Cybereason Bazar July 2020](https://www.cybereason.com/blog/a-bazar-of-tricks-following-team9s-development-cycles) · [NCC Group Team9 June 2020](https://research.nccgroup.com/2020/06/02/in-depth-analysis-of-the-new-team9-malware-family/)
- [G0077 - Leafminer](../../../../Threat%20Intelligence/Groups/G0077%20-%20Leafminer.md) — [Leafminer](https://attack.mitre.org/groups/G0077) has used [Process Doppelgänging](https://attack.mitre.org/techniques/T1055/013) to evade security software while deploying tools on compromised systems.(Citation: Symantec Leafminer July 2018) [Symantec Leafminer July 2018](https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east)
- [S0242 - SynAck](../../../../Threat%20Intelligence/Software/Malware/S0242%20-%20SynAck.md) — [SynAck](https://attack.mitre.org/software/S0242) abuses NTFS transactions to launch and conceal malicious processes.(Citation: SecureList SynAck Doppelgänging May 2018)(Citation: Kaspersky Lab SynAck May 2018) [SecureList SynAck Doppelgänging May 2018](https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/) · [Kaspersky Lab SynAck May 2018](https://usa.kaspersky.com/about/press-releases/2018_synack-doppelganging)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.

## Detection strategies

- [DET0544 - Detection Strategy for Process Doppelgänging on Windows](../../../../Defenses/Detection%20Strategies/DET0544%20-%20Detection%20Strategy%20for%20Process%20Doppelg%C3%A4nging%20on%20Windows.md)

## Sources

- [BlackHat Process Doppelgänging Dec 2017](https://www.blackhat.com/docs/eu-17/materials/eu-17-Liberman-Lost-In-Transaction-Process-Doppelganging.pdf)
- [Microsoft Basic TxF Concepts](https://msdn.microsoft.com/library/windows/desktop/dd979526.aspx)
- [Microsoft TxF](https://msdn.microsoft.com/library/windows/desktop/bb968806.aspx)
- [Microsoft Where to use TxF](https://msdn.microsoft.com/library/windows/desktop/aa365738.aspx)
