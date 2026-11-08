# DC0113 - Network Communication

[Mobile](../../README.md) / [Data Components](README.md)

Network Communication captures outbound or inbound communication initiated by an application or mobile device, including the domains contacted, protocols used, and session metadata associated with the communication.

Monitoring network communication enables defenders to identify command-and-control traffic, data exfiltration, or suspicious communication patterns originating from mobile applications.

Examples

- Connections to previously unseen domains
- Repeated communication with suspicious infrastructure
- Communication immediately following application installation

Collection Methods

- Mobile VPN telemetry
- Secure web gateway logs
- Network detection and response (NDR)
- Mobile EDR network monitoring

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0113)

## Log sources and channels

- **iOS:NetworkExtension** — NEFilterFlow, per-app VPN, or secure web gateway flow metadata
- **android:EnterpriseNetworkLog** — DevicePolicyManager.retrieveNetworkLogs(): DnsEvent / ConnectEvent; VPN flow metadata
- **Application Vetting** — None
- **iOS:NetworkExtension** — NEFilterFlow / per-app VPN / secure-web-gateway flow metadata

## Analytics using this component

- [AN1753 - Analytic 1753](../Analytics/AN1753.md)
- [AN1754 - Analytic 1754](../Analytics/AN1754.md)
- [AN2290 - Analytic 2290](../Analytics/AN2290.md)
- [AN2291 - Analytic 2291](../Analytics/AN2291.md)
