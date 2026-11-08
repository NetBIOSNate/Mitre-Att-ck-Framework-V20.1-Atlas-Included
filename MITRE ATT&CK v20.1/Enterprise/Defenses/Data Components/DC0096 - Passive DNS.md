# DC0096 - Passive DNS

[Enterprise](../../README.md) / [Data Components](README.md)

"Domain Name: Passive DNS" captures logged historical and real-time domain name system (DNS) data. This includes records of domain-to-IP address resolutions over time, enabling analysts to track the evolution of domain infrastructure, uncover historical patterns of use, and detect malicious activities tied to domains and their associated IP addresses. Examples: 

- Historical Resolutions
- Shared IP Usage
- Temporal Patterns
- Malicious Domain Clustering
- Historical Lookback

This data component can be collected through the following measures:

- Passive DNS Platforms: Use platforms that specialize in passive DNS collection and analysis:
   - Tools: Farsight DNSDB, RiskIQ PassiveTotal, PassiveDNS.
- Threat Intelligence Feeds: Integrate passive DNS data from commercial or open-source threat intelligence providers.
- Custom DNS Collectors: Deploy custom tools to capture DNS traffic at the network level for analysis.
- Cloud DNS Services: Leverage cloud DNS services (e.g., AWS Route 53, Azure DNS) that maintain DNS query logs.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0096)

## Log sources and channels

- **Domain Name** — None

## Analytics using this component

- [AN1995 - Analytic 1995](../Analytics/AN1995.md)
- [AN2017 - Analytic 2017](../Analytics/AN2017.md)
- [AN2023 - Analytic 2023](../Analytics/AN2023.md)
- [AN2024 - Analytic 2024](../Analytics/AN2024.md)
- [AN2027 - Analytic 2027](../Analytics/AN2027.md)
