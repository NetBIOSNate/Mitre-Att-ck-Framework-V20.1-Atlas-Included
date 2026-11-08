# T1668 - Exclusive Control

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries who successfully compromise a system may attempt to maintain persistence by “closing the door” behind them  – in other words, by preventing other threat actors from initially accessing or maintaining a foothold on the same system. 

For example, adversaries may patch a vulnerable, compromised system(Citation: Mandiant-iab-control)(Citation: CERT AT Fortinent Ransomware 2025) to prevent other threat actors from leveraging that vulnerability in the future. They may “close the door” in other ways, such as disabling vulnerable services(Citation: sophos-multiple-attackers), stripping privileges from accounts(Citation: aquasec-postgres-processes), or removing other malware already on the compromised device.(Citation: fsecure-netsky)

Hindering other threat actors may allow an adversary to maintain sole access to a compromised system or network. This prevents the threat actor from needing to compete with or even being removed themselves by other threat actors. It also reduces the “noise” in the environment, lowering the possibility of being caught and evicted by defenders. Finally, in the case of [Resource Hijacking](https://attack.mitre.org/techniques/T1496), leveraging a compromised device’s full power allows the threat actor to maximize profit.(Citation: sophos-multiple-attackers)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1668)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Detection strategies

- [DET0015 - Detection Strategy for Exclusive Control](../../../Defenses/Detection%20Strategies/DET0015%20-%20Detection%20Strategy%20for%20Exclusive%20Control.md)

## Sources

- [aquasec-postgres-processes](https://www.aquasec.com/blog/pg_mem-a-malware-hidden-in-the-postgres-processes/)
- [CERT AT Fortinent Ransomware 2025](https://www.cert.at/de/warnungen/2025/3/ransomware-gruppen-nutzen-weiterhin-kritische-fortinet-schwachstellen-warnung-vor-gepatchten-aber-bereits-kompromittierten-geraten)
- [fsecure-netsky](https://www.f-secure.com/v-descs/netsky-h.shtml)
- [sophos-multiple-attackers](https://news.sophos.com/en-us/2022/08/09/multiple-attackers-increase-pressure-on-victims-complicate-incident-response/#:~:text=While%20some%20threat%20actors%20are%20interdependent%20%28e.g.%2C%20IABs,vulnerabilities%20or%20disabling%20vulnerable%20services%20after%20gaining%20access)
- [Mandiant-iab-control](https://cloud.google.com/blog/topics/threat-intelligence/initial-access-brokers-exploit-f5-screenconnect)
