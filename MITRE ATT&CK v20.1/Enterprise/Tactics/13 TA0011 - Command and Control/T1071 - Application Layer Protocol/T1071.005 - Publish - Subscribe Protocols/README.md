# T1071.005 - Publish/Subscribe Protocols

[Enterprise](../../../../README.md) / [Command and Control](../../README.md) / [T1071 - Application Layer Protocol](../README.md)

Adversaries may communicate using publish/subscribe (pub/sub) application layer protocols to avoid detection/network filtering by blending in with existing traffic. Commands to the remote system, and often the results of those commands, will be embedded within the protocol traffic between the client and server. 

Protocols such as <code>MQTT</code>, <code>XMPP</code>, <code>AMQP</code>, and <code>STOMP</code> use a publish/subscribe design, with message distribution managed by a centralized broker.(Citation: wailing crab sub/pub)(Citation: Mandiant APT1 Appendix) Publishers categorize their messages by topics, while subscribers receive messages according to their subscribed topics.(Citation: wailing crab sub/pub) An adversary may abuse publish/subscribe protocols to communicate with systems under their control from behind a message broker while also mimicking normal, expected traffic.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1071/005)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md), [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

## Detection strategies

- [DET0002 - Behavioral Detection of Publish/Subscribe Protocol Misuse for C2](../../../../Defenses/Detection%20Strategies/DET0002%20-%20Behavioral%20Detection%20of%20Publish%20-%20Subscribe%20Protocol%20Misuse%20for%20C2.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Consider filtering publish/subscribe protocol requests to untrusted or known bad resources over irregular ports (e.g. MQTT’s standard ports are 1883 or 8883).
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level.

## Procedure examples

- [S0026 - GLOOXMAIL](../../../../Threat%20Intelligence/Software/Malware/S0026%20-%20GLOOXMAIL.md) — [GLOOXMAIL](https://attack.mitre.org/software/S0026) communicates to servers operated by Google using the Jabber/XMPP protocol for C2.(Citation: Mandiant APT1 Appendix) [Mandiant APT1 Appendix](https://www.mandiant.com/sites/default/files/2021-09/mandiant-apt1-report.pdf)

## Sources

- [wailing crab sub/pub](https://securityintelligence.com/x-force/wailingcrab-malware-misues-mqtt-messaging-protocol/)
- [Mandiant APT1 Appendix](https://www.mandiant.com/sites/default/files/2021-09/mandiant-apt1-report.pdf)
