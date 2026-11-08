# T1568.003 - DNS Calculation

[Enterprise](../../../../README.md) / [Command and Control](../../README.md) / [T1568 - Dynamic Resolution](../README.md)

Adversaries may perform calculations on addresses returned in DNS results to determine which port and IP address to use for command and control, rather than relying on a predetermined port number or the actual returned IP address. An IP and/or port number calculation can be used to bypass egress filtering on a C2 channel.(Citation: Meyers Numbered Panda)

One implementation of [DNS Calculation](https://attack.mitre.org/techniques/T1568/003) is to take the first three octets of an IP address in a DNS response and use those values to calculate the port for command and control traffic.(Citation: Meyers Numbered Panda)(Citation: Moran 2014)(Citation: Rapid7G20Espionage)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1568/003)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [ESXi](../../../../Platforms/ESXi.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0005 - APT12](../../../../Threat%20Intelligence/Groups/G0005%20-%20APT12.md) — [APT12](https://attack.mitre.org/groups/G0005) has used multiple variants of [DNS Calculation](https://attack.mitre.org/techniques/T1568/003) including multiplying the first two octets of an IP address and adding the third octet to that value in order to get a resulting command and control port.(Citation: Meyers Numbered Panda) [Meyers Numbered Panda](http://www.crowdstrike.com/blog/whois-numbered-panda/)

## Detection strategies

- [DET0262 - Detection Strategy for Dynamic Resolution through DNS Calculation](../../../../Defenses/Detection%20Strategies/DET0262%20-%20Detection%20Strategy%20for%20Dynamic%20Resolution%20through%20DNS%20Calculation.md)

## Sources

- [Meyers Numbered Panda](http://www.crowdstrike.com/blog/whois-numbered-panda/)
- [Moran 2014](https://www.fireeye.com/blog/threat-research/2014/09/darwins-favorite-apt-group-2.html)
- [Rapid7G20Espionage](https://blog.rapid7.com/2013/08/26/upcoming-g20-summit-fuels-espionage-operations/)
