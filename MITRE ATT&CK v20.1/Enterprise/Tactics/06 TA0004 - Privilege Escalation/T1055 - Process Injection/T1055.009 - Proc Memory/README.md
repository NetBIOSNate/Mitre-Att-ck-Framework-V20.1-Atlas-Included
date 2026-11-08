# T1055.009 - Proc Memory

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject malicious code into processes via the /proc filesystem in order to evade process-based defenses as well as possibly elevate privileges. Proc memory injection is a method of executing arbitrary code in the address space of a separate live process. 

Proc memory injection involves enumerating the memory of a process via the /proc filesystem (<code>/proc/[pid]</code>) then crafting a return-oriented programming (ROP) payload with available gadgets/instructions. Each running process has its own directory, which includes memory mappings. Proc memory injection is commonly performed by overwriting the target processes’ stack using memory mappings provided by the /proc filesystem. This information can be used to enumerate offsets (including the stack) and gadgets (or instructions within the program that can be used to build a malicious payload) otherwise hidden by process memory protections such as address space layout randomization (ASLR). Once enumerated, the target processes’ memory map within <code>/proc/[pid]/maps</code> can be overwritten using dd.(Citation: Uninformed Needle)(Citation: GDS Linux Injection)(Citation: DD Man) 

Other techniques such as [Dynamic Linker Hijacking](https://attack.mitre.org/techniques/T1574/006) may be used to populate a target process with more available gadgets. Similar to [Process Hollowing](https://attack.mitre.org/techniques/T1055/012), proc memory injection may target child processes (such as a backgrounded copy of sleep).(Citation: GDS Linux Injection) 

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via proc memory injection may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/009)

**Tactics**  [Privilege Escalation](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict the permissions on sensitive files such as <code>/proc/[pid]/maps</code> or <code>/proc/[pid]/mem</code>.

## Detection strategies

- [DET0541 - Detection Strategy for /proc Memory Injection on Linux](../../../../Defenses/Detection%20Strategies/DET0541%20-%20Detection%20Strategy%20for%20-%20proc%20Memory%20Injection%20on%20Linux.md)

## Procedure examples

- [C0035 - KV Botnet Activity](../../../../Threat%20Intelligence/Campaigns/C0035%20-%20KV%20Botnet%20Activity.md) — [KV Botnet Activity](https://attack.mitre.org/campaigns/C0035) final payload installation includes mounting and binding to the <code>\/proc\/</code> filepath on the victim system to enable subsequent operation in memory while also removing on-disk artifacts.(Citation: Lumen KVBotnet 2023) [Lumen KVBotnet 2023](https://blog.lumen.com/routers-roasting-on-an-open-firewall-the-kv-botnet-investigation/)

## Sources

- [DD Man](http://man7.org/linux/man-pages/man1/dd.1.html)
- [GDS Linux Injection](https://blog.gdssecurity.com/labs/2017/9/5/linux-based-inter-process-code-injection-without-ptrace2.html)
- [Uninformed Needle](http://hick.org/code/skape/papers/needle.txt)
