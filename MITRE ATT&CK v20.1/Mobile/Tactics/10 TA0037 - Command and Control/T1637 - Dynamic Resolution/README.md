# T1637 - Dynamic Resolution

[Mobile](../../../README.md) / [Command and Control](../README.md)

Adversaries may dynamically establish connections to command and control infrastructure to evade common detections and remediations. This may be achieved by using malware that shares a common algorithm with the infrastructure the adversary uses to receive the malware's communications. This algorithm can be used to dynamically adjust parameters such as the domain name, IP address, or port number the malware uses for command and control.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1637)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1637.001 - Domain Generation Algorithms](T1637.001%20-%20Domain%20Generation%20Algorithms/README.md)

## Detection strategies

- [DET0613 - Detection of Dynamic Resolution](../../../Defenses/Detection%20Strategies/DET0613%20-%20Detection%20of%20Dynamic%20Resolution.md)

## Sources

- [Data Driven Security DGA](https://datadrivensecurity.info/blog/posts/2014/Oct/dga-part2/)
