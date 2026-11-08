# AML.S0030 - Shodan

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[Shodan](AML.S0030%20-%20Shodan.md) is a search service for internet-connected devices and services. It collects and indexes service banners and associated metadata, including IP addresses, hostnames, open ports, software information, and HTTP content. Its web interface and API support filtered searches, host lookups, and monitoring of internet-facing infrastructure. [shodan-api](https://developer.shodan.io/api)[[product-overview]]

**Software type**  Tool

**Software categories**  service

## Used by

- [AML.CS0048 - Exposed ClawdBot Control Interfaces Leads to Credential Access and Execution](../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md) — The researcher used [Shodan](AML.S0030%20-%20Shodan.md) to search for the "Clawdbot Control" page title and locate internet-facing ClawdBot administration interfaces. The resulting hosts provided candidates for subsequent authentication and configuration-exposure testing. [x](https://x.com/theonejvo/status/2015401219746128322)
- [AML.E0020 - HiddenLayer](../../Entities/AML.E0020%20-%20HiddenLayer.md) — [HiddenLayer](../../Entities/AML.E0020%20-%20HiddenLayer.md) researchers used [Shodan](AML.S0030%20-%20Shodan.md) to identify internet-facing OpenClaw gateways and instances exposing OpenClaw-related mDNS discovery information. [openclaw-sec-risks](https://www.hiddenlayer.com/research/exploring-the-security-risks-of-ai-assistants-like-openclaw)

## Techniques implemented

- [AML.T0000.003 - Scan Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/AML.T0000.003%20-%20Scan%20Databases/README.md) — [Shodan](AML.S0030%20-%20Shodan.md) provides searchable internet-scan results containing service banners, HTTP titles, software identifiers, IP addresses, and open ports. Its web interface and API allow users to locate exposed AI services and supporting infrastructure by querying indexed fingerprints without directly probing each target.[[source-1]]

## References

- [Shodan API documentation](https://developer.shodan.io/api)
- [What is Shodan?](https://help.shodan.io/the-basics/what-is-shodan)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0030)
