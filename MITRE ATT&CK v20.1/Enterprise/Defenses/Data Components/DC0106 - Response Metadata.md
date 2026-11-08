# DC0106 - Response Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Contextual information about an Internet-facing resource collected during a scan, including details such as open ports, running services, protocols, and versions. This metadata is typically derived from interpreting scan results and helps build a profile of the targeted system. Examples: 

- Port and Service Details:
    - Open ports (e.g., 22, 80, 443).
    - Identified services running on those ports (e.g., SSH, HTTP, HTTPS).
- Service Versions: Detected software version information (e.g., Apache 2.4.41, OpenSSH 8.2).
- Operating System Information: OS fingerprinting data (e.g., Linux Kernel 5.4.0).
- TLS/SSL Certificate Data: Information about the TLS/SSL certificate, such as the expiration date, issuer, and cipher suites.

*Data Collection Measures:*

- Scanning Tools:
    - Nmap: Collects port, service, and version information using commands like nmap -sV <IP>.
    - Masscan: High-speed scanning tool for discovering open ports and active services.
    - Zmap: Focused on large-scale Internet scanning, collecting metadata about discovered services.
    - Shodan API: Retrieves scan metadata for publicly exposed devices and services.
- Network Logs:
    - Use logs from firewalls, intrusion detection systems (IDS), or intrusion prevention systems (IPS) to gather metadata from scan attempts. Example: Zeek or Suricata logs for incoming scan traffic.
- OSINT Platforms: Platforms like Censys, GreyNoise, or Shodan provide aggregated metadata about Internet-facing resources.
- Cloud Metadata Services: AWS Security Hub, Azure Monitor, or GCP Security Command Center can collect and centralize scan-related metadata for Internet-facing resources in cloud environments.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0106)

## Log sources and channels

- **Internet Scan** — None
- **NSM:Flow** — Altered response metadata or blocked content based on user-agent or geolocation

## Analytics using this component

- [AN1149 - Analytic 1149](../Analytics/AN1149.md)
- [AN1970 - Analytic 1970](../Analytics/AN1970.md)
- [AN1986 - Analytic 1986](../Analytics/AN1986.md)
- [AN2003 - Analytic 2003](../Analytics/AN2003.md)
- [AN2006 - Analytic 2006](../Analytics/AN2006.md)
- [AN2017 - Analytic 2017](../Analytics/AN2017.md)
- [AN2027 - Analytic 2027](../Analytics/AN2027.md)
