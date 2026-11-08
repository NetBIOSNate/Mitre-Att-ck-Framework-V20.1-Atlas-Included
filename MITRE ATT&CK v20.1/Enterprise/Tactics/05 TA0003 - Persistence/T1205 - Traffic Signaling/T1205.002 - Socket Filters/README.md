# T1205.002 - Socket Filters

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1205 - Traffic Signaling](../README.md)

Adversaries may attach filters to a network socket to monitor then activate backdoors used for persistence or command and control. With elevated permissions, adversaries can use features such as the `libpcap` library to open sockets and install filters to allow or disallow certain types of data to come through the socket. The filter may apply to all traffic passing through the specified network interface (or every interface if not specified). When the network interface receives a packet matching the filter criteria, additional actions can be triggered on the host, such as activation of a reverse shell.

To establish a connection, an adversary sends a crafted packet to the targeted host that matches the installed filter criteria.(Citation: haking9 libpcap network sniffing) Adversaries have used these socket filters to trigger the installation of implants, conduct ping backs, and to invoke command shells. Communication with these socket filters may also be used in conjunction with [Protocol Tunneling](https://attack.mitre.org/techniques/T1572).(Citation: exatrack bpf filters passive backdoors)(Citation: Leonardo Turla Penquin May 2020)

Filters can be installed on any Unix-like platform with `libpcap` installed or on Windows hosts using `Winpcap`.  Adversaries may use either `libpcap` with `pcap_setfilter` or the standard library function `setsockopt` with `SO_ATTACH_FILTER` options. Since the socket connection is not active until the packet is received, this behavior may be difficult to detect due to the lack of activity on a host, low CPU overhead, and limited visibility into raw socket usage.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1205/002)

**Tactics**  [Persistence](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md), [Command and Control](../../../13%20TA0011%20-%20Command%20and%20Control/README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S1161 - BPFDoor](../../../../Threat%20Intelligence/Software/Malware/S1161%20-%20BPFDoor.md) — [BPFDoor](https://attack.mitre.org/software/S1161) uses BPF bytecode to attach a filter to a network socket to view ICMP, UDP, or TCP packets coming through ports 22 (ssh), 80 (http), and 443 (https). When [BPFDoor](https://attack.mitre.org/software/S1161) finds a packet containing its “magic” bytes, it parses out two fields and forks itself. The parent process continues to monitor filtered traffic while the child process executes the instructions from the parsed fields.(Citation: Sandfly BPFDoor 2022)(Citation: Deep Instinct BPFDoor 2023) [Deep Instinct BPFDoor 2023](https://www.deepinstinct.com/blog/bpfdoor-malware-evolves-stealthy-sniffing-backdoor-ups-its-game) · [Sandfly BPFDoor 2022](https://sandflysecurity.com/blog/bpfdoor-an-evasive-linux-backdoor-technical-analysis/)
- [S1224 - CASTLETAP](../../../../Threat%20Intelligence/Software/Malware/S1224%20-%20CASTLETAP.md) — [CASTLETAP](https://attack.mitre.org/software/S1224) can listen for a specialized ICMP packet for activation on compromised network devices.(Citation: Mandiant Fortinet Zero Day) [Mandiant Fortinet Zero Day](https://www.mandiant.com/resources/blog/fortinet-malware-ecosystem)
- [S0587 - Penquin](../../../../Threat%20Intelligence/Software/Malware/S0587%20-%20Penquin.md) — [Penquin](https://attack.mitre.org/software/S0587) installs a `TCP` and `UDP` filter on the `eth0` interface.(Citation: Leonardo Turla Penquin May 2020) [Leonardo Turla Penquin May 2020](https://www.leonardo.com/documents/20142/10868623/Malware+Technical+Insight+_Turla+%E2%80%9CPenquin_x64%E2%80%9D.pdf)
- [S1123 - PITSTOP](../../../../Threat%20Intelligence/Software/Malware/S1123%20-%20PITSTOP.md) — [PITSTOP](https://attack.mitre.org/software/S1123) can listen and evaluate incoming commands on the domain socket, created by PITHOOK malware, located at `/data/runtime/cockpit/wd.fd` for a predefined magic byte sequence. [PITSTOP](https://attack.mitre.org/software/S1123) can then duplicate the socket for further communication over TLS.(Citation: Mandiant Cutting Edge Part 3 February 2024) [Mandiant Cutting Edge Part 3 February 2024](https://www.mandiant.com/resources/blog/investigating-ivanti-exploitation-persistence)

## Detection strategies

- [DET0162 - Socket-filter trigger → on-host raw-socket activity → reverse connection (T1205.002)](../../../../Defenses/Detection%20Strategies/DET0162%20-%20Socket-filter%20trigger%20%E2%86%92%20on-host%20raw-socket%20activity%20%E2%86%92%20reverse%20connection%20%28T1205.002%29.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Mitigation of some variants of this technique could be achieved through the use of stateful firewalls, depending upon how it is implemented.

## Sources

- [exatrack bpf filters passive backdoors](https://exatrack.com/public/Tricephalic_Hellkeeper.pdf)
- [Leonardo Turla Penquin May 2020](https://www.leonardo.com/documents/20142/10868623/Malware+Technical+Insight+_Turla+%E2%80%9CPenquin_x64%E2%80%9D.pdf)
- [haking9 libpcap network sniffing](http://recursos.aldabaknocking.com/libpcapHakin9LuisMartinGarcia.pdf)
