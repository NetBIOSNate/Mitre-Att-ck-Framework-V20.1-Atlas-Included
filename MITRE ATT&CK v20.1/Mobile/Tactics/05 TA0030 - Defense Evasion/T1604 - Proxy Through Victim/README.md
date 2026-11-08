# T1604 - Proxy Through Victim

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may use a compromised device as a proxy server to the Internet. By utilizing a proxy, adversaries hide the true IP address of their C2 server and associated infrastructure from the destination of the network traffic. This masquerades an adversary’s traffic as legitimate traffic originating from the compromised device, which can evade IP-based restrictions and alerts on certain services, such as bank accounts and social media websites.(Citation: Threat Fabric Exobot)

The most common type of proxy is a SOCKS proxy. It can typically be implemented using standard OS-level APIs and 3rd party libraries with no indication to the user. On Android, adversaries can use the `Proxy` API to programmatically establish a SOCKS proxy connection, or lower-level APIs to interact directly with raw sockets.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1604)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S0522 - Exobot](../../../Threat%20Intelligence/Software/Malware/S0522%20-%20Exobot.md) — [Exobot](https://attack.mitre.org/software/S0522) can open a SOCKS proxy connection through the compromised device.(Citation: Threat Fabric Exobot) [Threat Fabric Exobot](https://www.threatfabric.com/blogs/exobot_android_banking_trojan_on_the_rise.html)
- [S1067 - FluBot](../../../Threat%20Intelligence/Software/Malware/S1067%20-%20FluBot.md) — [FluBot](https://attack.mitre.org/software/S1067) can use a SOCKS proxy to evade C2 IP detection.(Citation: proofpoint_flubot_0421) [proofpoint_flubot_0421](https://www.proofpoint.com/us/blog/threat-insight/flubot-android-malware-spreading-rapidly-through-europe-may-hit-us-soon)

## Detection strategies

- [DET0631 - Detection of Proxy Through Victim](../../../Defenses/Detection%20Strategies/DET0631%20-%20Detection%20of%20Proxy%20Through%20Victim.md)

## Sources

- [Threat Fabric Exobot](https://www.threatfabric.com/blogs/exobot_android_banking_trojan_on_the_rise.html)
