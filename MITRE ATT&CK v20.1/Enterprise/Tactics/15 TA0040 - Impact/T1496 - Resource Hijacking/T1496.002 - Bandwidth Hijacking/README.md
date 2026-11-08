# T1496.002 - Bandwidth Hijacking

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1496 - Resource Hijacking](../README.md)

Adversaries may leverage the network bandwidth resources of co-opted systems to complete resource-intensive tasks, which may impact system and/or hosted service availability. 

Adversaries may also use malware that leverages a system's network bandwidth as part of a botnet in order to facilitate [Network Denial of Service](https://attack.mitre.org/techniques/T1498) campaigns and/or to seed malicious torrents.(Citation: GoBotKR) Alternatively, they may engage in proxyjacking by selling use of the victims' network bandwidth and IP address to proxyware services.(Citation: Sysdig Proxyjacking) Finally, they may engage in internet-wide scanning in order to identify additional targets for compromise.(Citation: Unit 42 Leaked Environment Variables 2024)

In addition to incurring potential financial costs or availability disruptions, this technique may cause reputational damage if a victim’s bandwidth is used for illegal activities.(Citation: Sysdig Proxyjacking)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1496/002)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md), [IaaS](../../../../Platforms/IaaS.md), [Containers](../../../../Platforms/Containers.md)

## Detection strategies

- [DET0028 - Detect Excessive or Unauthorized Bandwidth Usage for Botnet, Proxyjacking, or Scanning Purposes](../../../../Defenses/Detection%20Strategies/DET0028%20-%20Detect%20Excessive%20or%20Unauthorized%20Bandwidth%20Usage%20for%20Botnet%2C%20Proxyjacking%2C%20or%20Scannin.md)

## Sources

- [Sysdig Proxyjacking](https://sysdig.com/blog/proxyjacking-attackers-log4j-exploited/)
- [Unit 42 Leaked Environment Variables 2024](https://unit42.paloaltonetworks.com/large-scale-cloud-extortion-operation/)
- [GoBotKR](https://www.welivesecurity.com/2019/07/08/south-korean-users-backdoor-torrents/)
