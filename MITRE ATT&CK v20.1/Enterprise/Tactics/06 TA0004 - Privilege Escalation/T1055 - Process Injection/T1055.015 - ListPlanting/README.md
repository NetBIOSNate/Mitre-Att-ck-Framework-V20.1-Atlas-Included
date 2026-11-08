# T1055.015 - ListPlanting

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may abuse list-view controls to inject malicious code into hijacked processes in order to evade process-based defenses as well as possibly elevate privileges. ListPlanting is a method of executing arbitrary code in the address space of a separate live process.(Citation: Hexacorn Listplanting) Code executed via ListPlanting may also evade detection from security products since the execution is masked under a legitimate process.

List-view controls are user interface windows used to display collections of items.(Citation: Microsoft List View Controls) Information about an application's list-view settings is stored within the process' memory in a <code>SysListView32</code> control.

ListPlanting (a form of message-passing "shatter attack") may be performed by copying code into the virtual address space of a process that uses a list-view control then using that code as a custom callback for sorting the listed items.(Citation: Modexp Windows Process Injection) Adversaries must first copy code into the target process’ memory space, which can be performed various ways including by directly obtaining a handle to the <code>SysListView32</code> child of the victim process window (via Windows API calls such as <code>FindWindow</code> and/or <code>EnumWindows</code>) or other [Process Injection](https://attack.mitre.org/techniques/T1055) methods.

Some variations of ListPlanting may allocate memory in the target process but then use window messages to copy the payload, to avoid the use of the highly monitored <code>WriteProcessMemory</code> function. For example, an adversary can use the <code>PostMessage</code> and/or <code>SendMessage</code> API functions to send <code>LVM_SETITEMPOSITION</code> and <code>LVM_GETITEMPOSITION</code> messages, effectively copying a payload 2 bytes at a time to the allocated memory.(Citation: ESET InvisiMole June 2020) 

Finally, the payload is triggered by sending the <code>LVM_SORTITEMS</code> message to the <code>SysListView32</code> child of the process window, with the payload within the newly allocated buffer passed and executed as the <code>ListView_SortItems</code> callback.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/015)

**Tactics**  [Privilege Escalation](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0331 - Detection Strategy for ListPlanting Injection on Windows](../../../../Defenses/Detection%20Strategies/DET0331%20-%20Detection%20Strategy%20for%20ListPlanting%20Injection%20on%20Windows.md)

## Procedure examples

- [S0260 - InvisiMole](../../../../Threat%20Intelligence/Software/Malware/S0260%20-%20InvisiMole.md) — [InvisiMole](https://attack.mitre.org/software/S0260) has used ListPlanting to inject code into a trusted process.(Citation: ESET InvisiMole June 2020) [ESET InvisiMole June 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_InvisiMole.pdf)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.

## Sources

- [Hexacorn Listplanting](https://www.hexacorn.com/blog/2019/04/25/listplanting-yet-another-code-injection-trick/)
- [ESET InvisiMole June 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_InvisiMole.pdf)
- [Microsoft List View Controls](https://docs.microsoft.com/windows/win32/controls/list-view-controls-overview)
- [Modexp Windows Process Injection](https://modexp.wordpress.com/2019/04/25/seven-window-injection-methods/)
