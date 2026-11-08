# T1200 - Hardware Additions

[Enterprise](../../../README.md) / [Initial Access](../README.md)

Adversaries may physically introduce computer accessories, networking hardware, or other computing devices into a system or network that can be used as a vector to gain access. Rather than just connecting and distributing payloads via removable storage (i.e. [Replication Through Removable Media](https://attack.mitre.org/techniques/T1091)), more robust hardware additions can be used to introduce new functionalities and/or features into a system that can then be abused.

While public references of usage by threat actors are scarce, many red teams/penetration testers leverage hardware additions for initial access. Commercial and open source products can be leveraged with capabilities such as passive network tapping, network traffic modification (i.e. [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557)), keystroke injection, kernel memory reading via DMA, addition of new wireless access points to an existing network, and others.(Citation: Ossmann Star Feb 2011)(Citation: Aleks Weapons Nov 2015)(Citation: Frisk DMA August 2016)(Citation: McMillan Pwn March 2012)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1200)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md)

## Procedure examples

- [G0105 - DarkVishnya](../../../Threat%20Intelligence/Groups/G0105%20-%20DarkVishnya.md) — [DarkVishnya](https://attack.mitre.org/groups/G0105) physically connected Bash Bunny, Raspberry Pi, netbooks, and inexpensive laptops to the target organization's environment to access the company’s local network.(Citation: Securelist DarkVishnya Dec 2018) [Securelist DarkVishnya Dec 2018](https://securelist.com/darkvishnya/89169/)

## Mitigations

- [M1035 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Establish network access control policies, such as using device certificates and the 802.1x standard. (Citation: Wikipedia 802.1x) Restrict use of DHCP to registered devices to prevent unregistered devices from communicating with trusted systems. [Wikipedia 802.1x](https://en.wikipedia.org/wiki/IEEE_802.1X)
- [M1034 - Limit Hardware Installation](../../../Defenses/Mitigations/M1034%20-%20Limit%20Hardware%20Installation.md) — Block unknown devices and accessories by endpoint security configuration and monitoring agent.

## Detection strategies

- [DET0069 - Detect unauthorized or suspicious Hardware Additions (USB/Thunderbolt/Network)](../../../Defenses/Detection%20Strategies/DET0069%20-%20Detect%20unauthorized%20or%20suspicious%20Hardware%20Additions%20%28USB%20-%20Thunderbolt%20-%20Network%29.md)

## Sources

- [Ossmann Star Feb 2011](https://ossmann.blogspot.com/2011/02/throwing-star-lan-tap.html)
- [Aleks Weapons Nov 2015](https://www.youtube.com/watch?v=lDvf4ScWbcQ)
- [McMillan Pwn March 2012](https://arstechnica.com/information-technology/2012/03/the-pwn-plug-is-a-little-white-box-that-can-hack-your-network/)
- [Frisk DMA August 2016](https://www.youtube.com/watch?v=fXthwl6ShOg)
