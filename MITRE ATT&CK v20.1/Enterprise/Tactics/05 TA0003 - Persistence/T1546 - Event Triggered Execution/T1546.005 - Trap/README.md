# T1546.005 - Trap

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence by executing malicious content triggered by an interrupt signal. The <code>trap</code> command allows programs and shells to specify commands that will be executed upon receiving interrupt signals. A common situation is a script allowing for graceful termination and handling of common keyboard interrupts like <code>ctrl+c</code> and <code>ctrl+d</code>.

Adversaries can use this to register code to be executed when the shell encounters specific interrupts as a persistence mechanism. Trap commands are of the following format <code>trap 'command list' signals</code> where "command list" will be executed when "signals" are received.(Citation: Trap Manual)(Citation: Cyberciti Trap Statements)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/005)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md), [Linux](../../../../Platforms/Linux.md)

## Detection strategies

- [DET0369 - Detection Strategy for Event Triggered Execution via Trap (T1546.005)](../../../../Defenses/Detection%20Strategies/DET0369%20-%20Detection%20Strategy%20for%20Event%20Triggered%20Execution%20via%20Trap%20%28T1546.005%29.md)

## Sources

- [Trap Manual](https://ss64.com/bash/trap.html)
- [Cyberciti Trap Statements](https://bash.cyberciti.biz/guide/Trap_statement)
