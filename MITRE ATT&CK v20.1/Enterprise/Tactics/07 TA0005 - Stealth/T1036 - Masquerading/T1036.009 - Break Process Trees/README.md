# T1036.009 - Break Process Trees

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

An adversary may attempt to evade process tree-based analysis by modifying executed malware's parent process ID (PPID). If endpoint protection software leverages the “parent-child" relationship for detection, breaking this relationship could result in the adversary’s behavior not being associated with previous process tree activity. On Unix-based systems breaking this process tree is common practice for administrators to execute software using scripts and programs.(Citation: 3OHA double-fork 2022) 

On Linux systems, adversaries may execute a series of [Native API](https://attack.mitre.org/techniques/T1106) calls to alter malware's process tree. For example, adversaries can execute their payload without any arguments, call the `fork()` API call twice, then have the parent process exit. This creates a grandchild process with no parent process that is immediately adopted by the `init` system process (PID 1), which successfully disconnects the execution of the adversary's payload from its previous process tree.

Another example is using the “daemon” syscall to detach from the current parent process and run in the background.(Citation: Sandfly BPFDoor 2022)(Citation: Microsoft XorDdos Linux Stealth 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/009)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S1161 - BPFDoor](../../../../Threat%20Intelligence/Software/Malware/S1161%20-%20BPFDoor.md) — After initial execution, [BPFDoor](https://attack.mitre.org/software/S1161) forks itself and runs the fork with the `--init` flag, which allows it to execute secondary clean up operations. The parent process terminates leaving the forked process to be inherited by the legitimate process init.(Citation: Sandfly BPFDoor 2022) [Sandfly BPFDoor 2022](https://sandflysecurity.com/blog/bpfdoor-an-evasive-linux-backdoor-technical-analysis/)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has augmented its installation process by having its original install process exit cleanly to provide the user with the illusion that the service is installed normally.(Citation: Palo Alto Unit 42 Shai-Hulud November 2025)(Citation: Socket Shai-Hulud November 2025) [Palo Alto Unit 42 Shai-Hulud November 2025](https://unit42.paloaltonetworks.com/npm-supply-chain-attack/) · [Socket Shai-Hulud November 2025](https://socket.dev/blog/shai-hulud-strikes-again-v2)

## Detection strategies

- [DET0443 - Detection Strategy for Masquerading via Breaking Process Trees](../../../../Defenses/Detection%20Strategies/DET0443%20-%20Detection%20Strategy%20for%20Masquerading%20via%20Breaking%20Process%20Trees.md)

## Sources

- [3OHA double-fork 2022](https://0xjet.github.io/3OHA/2022/04/11/post.html)
- [Microsoft XorDdos Linux Stealth 2022](https://www.microsoft.com/en-us/security/blog/2022/05/19/rise-in-xorddos-a-deeper-look-at-the-stealthy-ddos-malware-targeting-linux-devices/)
- [Sandfly BPFDoor 2022](https://sandflysecurity.com/blog/bpfdoor-an-evasive-linux-backdoor-technical-analysis/)
