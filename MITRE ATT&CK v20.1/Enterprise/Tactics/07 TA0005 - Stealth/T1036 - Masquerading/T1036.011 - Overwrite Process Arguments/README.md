# T1036.011 - Overwrite Process Arguments

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

Adversaries may modify a process's in-memory arguments to change its name in order to appear as a legitimate or benign process. On Linux, the operating system stores command-line arguments in the process’s stack and passes them to the `main()` function as the `argv` array. The first element, `argv[0]`, typically contains the process name or path - by default, the command used to actually start the process (e.g., `cat /etc/passwd`). By default, the Linux `/proc` filesystem uses this value to represent the process name. The `/proc/<PID>/cmdline` file reflects the contents of this memory, and tools like `ps` use it to display process information. Since arguments are stored in user-space memory at launch, this modification can be performed without elevated privileges. 

During runtime, adversaries can erase the memory used by all command-line arguments for a process, overwriting each argument string with null bytes. This removes evidence of how the process was originally launched. They can then write a spoofed string into the memory region previously occupied by `argv[0]` to mimic a benign command, such as `cat resolv.conf`. The new command-line string is reflected in `/proc/<PID>/cmdline` and displayed by tools like `ps`.(Citation: Sandfly BPFDoor 2022)(Citation: Microsoft XorDdos Linux Stealth 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/011)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Procedure examples

- [S1161 - BPFDoor](../../../../Threat%20Intelligence/Software/Malware/S1161%20-%20BPFDoor.md) — [BPFDoor](https://attack.mitre.org/software/S1161) overwrites the `argv[0]` value used by the Linux `/proc` filesystem to determine the command line and command name to display for each process. [BPFDoor](https://attack.mitre.org/software/S1161) selects a name from 10 hardcoded names that resemble Linux system daemons, such as; `/sbin/udevd -d`, `dbus-daemon --system`, `avahi-daemon: chroot helper`, `/sbin/auditd -n`, and `/usr/lib/systemd/systemd-journald`.(Citation: Sandfly BPFDoor 2022) [Sandfly BPFDoor 2022](https://sandflysecurity.com/blog/bpfdoor-an-evasive-linux-backdoor-technical-analysis/)

## Detection strategies

- [DET0164 - Detection Strategy for Overwritten Process Arguments Masquerading](../../../../Defenses/Detection%20Strategies/DET0164%20-%20Detection%20Strategy%20for%20Overwritten%20Process%20Arguments%20Masquerading.md)

## Sources

- [Microsoft XorDdos Linux Stealth 2022](https://www.microsoft.com/en-us/security/blog/2022/05/19/rise-in-xorddos-a-deeper-look-at-the-stealthy-ddos-malware-targeting-linux-devices/)
- [Sandfly BPFDoor 2022](https://sandflysecurity.com/blog/bpfdoor-an-evasive-linux-backdoor-technical-analysis/)
