# T0847 - Replication Through Removable Media

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may move onto systems, such as those separated from the enterprise network, by copying malware to removable media which is inserted into the control systems environment. The adversary may rely on unknowing trusted third parties, such as suppliers or contractors with access privileges, to introduce the removable media. This technique enables initial access to target devices that never connect to untrusted networks, but are physically accessible.     

Operators of the German nuclear power plant, Gundremmingen, discovered malware on a facility computer not connected to the internet. (Citation: Kernkraftwerk Gundremmingen April 2016) (Citation: Trend Micro April 2016) The malware included Conficker and W32.Ramnit, which were also found on eighteen removable disk drives in the facility. (Citation: Christoph Steitz, Eric Auchard April 2016) (Citation: Catalin Cimpanu April 2016) (Citation: Peter Dockrill April 2016) (Citation: Lee Mathews April 2016) (Citation: Sean Gallagher April 2016) (Citation: Dark Reading Staff April 2016) The plant has since checked for infection and cleaned up more than 1,000 computers. (Citation: BBC April 2016) An ESET researcher commented that internet disconnection does not guarantee system safety from infection or payload execution. (Citation: ESET April 2016)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0847)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0733 - Detection of Replication Through Removable Media](../../../Defenses/Detection%20Strategies/DET0733%20-%20Detection%20of%20Replication%20Through%20Removable%20Media.md)

## Mitigations

- [M0942 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M0942%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider the disabling of features such as AutoRun.
- [M0934 - Limit Hardware Installation](../../../Defenses/Mitigations/M0934%20-%20Limit%20Hardware%20Installation.md) — Enforce system policies or physical restrictions to limit hardware such as USB devices on critical assets.
- [M0928 - Operating System Configuration](../../../Defenses/Mitigations/M0928%20-%20Operating%20System%20Configuration.md) — Harden the system through operating system controls to prevent the known or unknown use of malicious removable media.

## Procedure examples

- [S0608 - Conficker](../../../Threat%20Intelligence/Software/Malware/S0608%20-%20Conficker.md) — [Conficker](https://attack.mitre.org/software/S0608) exploits Windows drive shares. Once it has infected a computer, [Conficker](https://attack.mitre.org/software/S0608) automatically copies itself to all visible open drive shares on other computers inside the network. (Citation: Symantec June 2015) Nuclear power plant officials suspect someone brought in [Conficker](https://attack.mitre.org/software/S0608) by accident on a USB thumb drive, either from home or computers found in the power plant's facility. (Citation: Catalin Cimpanu April 2016) [Catalin Cimpanu April 2016](https://news.softpedia.com/news/on-chernobyl-s-30th-anniversary-malware-shuts-down-german-nuclear-power-plant-503429.shtml) · [Symantec June 2015](https://support.symantec.com/us/en/article.tech93179.html)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) was able to self-replicate by being spread through removable drives. A willing insider or unknown third party, such as a contractor, may have brought the removable media into the target environment. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) The earliest version of Stuxnet relied on physical installation, infecting target systems when an infected configuration file carried by a USB stick was opened. (Citation: Langer Stuxnet) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en) · [Langer Stuxnet](https://www.langner.com/wp-content/uploads/2017/03/to-kill-a-centrifuge.pdf)

## Sources

- [BBC April 2016](https://www.bbc.com/news/technology-36158606)
- [Catalin Cimpanu April 2016](https://news.softpedia.com/news/on-chernobyl-s-30th-anniversary-malware-shuts-down-german-nuclear-power-plant-503429.shtml)
- [Christoph Steitz, Eric Auchard April 2016](https://www.reuters.com/article/us-nuclearpower-cyber-germany/german-nuclear-plant-infected-with-computer-viruses-operator-says-idUSKCN0XN2OS)
- [Dark Reading Staff April 2016](https://www.darkreading.com/endpoint/german-nuclear-power-plant-infected-with-malware/d/d-id/1325298)
- [ESET April 2016](https://www.welivesecurity.com/2016/04/28/malware-found-german-nuclear-power-plant/)
- [Kernkraftwerk Gundremmingen April 2016](https://www.kkw-gundremmingen.de/presse.php?id=571)
- [Lee Mathews April 2016](https://web.archive.org/web/20160430041256/https://www.geek.com/apps/german-nuclear-plant-found-riddled-with-conficker-other-viruses-1653415/)
- [Peter Dockrill April 2016](https://www.sciencealert.com/multiple-computer-viruses-have-been-discovered-in-this-german-nuclear-plant)
- [Sean Gallagher April 2016](https://arstechnica.com/information-technology/2016/04/german-nuclear-plants-fuel-rod-system-swarming-with-old-malware/)
- [Trend Micro April 2016](https://www.trendmicro.com/vinfo/us/security/news/cyber-attacks/malware-discovered-in-german-nuclear-power-plant)
