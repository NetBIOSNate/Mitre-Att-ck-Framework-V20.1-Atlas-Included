# T1496 - Resource Hijacking

[Enterprise](../../../README.md) / [Impact](../README.md)

Adversaries may leverage the resources of co-opted systems to complete resource-intensive tasks, which may impact system and/or hosted service availability. 

Resource hijacking may take a number of different forms. For example, adversaries may:

* Leverage compute resources in order to mine cryptocurrency
* Sell network bandwidth to proxy networks
* Generate SMS traffic for profit
* Abuse cloud-based messaging services to send large quantities of spam messages

In some cases, adversaries may leverage multiple types of Resource Hijacking at once.(Citation: Sysdig Cryptojacking Proxyjacking 2023)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1496)

**Tactics**  [Impact](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [IaaS](../../../Platforms/IaaS.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Containers](../../../Platforms/Containers.md), [SaaS](../../../Platforms/SaaS.md)

## Sub-techniques

- [T1496.002 - Bandwidth Hijacking](T1496.002%20-%20Bandwidth%20Hijacking/README.md)
- [T1496.004 - Cloud Service Hijacking](T1496.004%20-%20Cloud%20Service%20Hijacking/README.md)
- [T1496.001 - Compute Hijacking](T1496.001%20-%20Compute%20Hijacking/README.md)
- [T1496.003 - SMS Pumping](T1496.003%20-%20SMS%20Pumping/README.md)

## Detection strategies

- [DET0267 - Resource Hijacking Detection Strategy](../../../Defenses/Detection%20Strategies/DET0267%20-%20Resource%20Hijacking%20Detection%20Strategy.md)

## Sources

- [Sysdig Cryptojacking Proxyjacking 2023](https://sysdig.com/blog/labrat-cryptojacking-proxyjacking-campaign/)
