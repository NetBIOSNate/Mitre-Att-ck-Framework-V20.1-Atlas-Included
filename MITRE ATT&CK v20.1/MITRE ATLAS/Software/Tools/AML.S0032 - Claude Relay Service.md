# AML.S0032 - Claude Relay Service

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[Claude Relay Service](AML.S0032%20-%20Claude%20Relay%20Service.md) is an open source, self-hosted API relay supporting Claude, Gemini, and OpenAI service access. It manages multiple upstream accounts, routes requests through account pools, and supports automatic account switching. Administrators can issue individual client API keys, configure usage limits, and monitor token consumption through a web interface. [source-1](https://github.com/Wei-Shaw/claude-relay-service)

**Software type**  Tool

**Aliases**  CRS

**Software categories**  program

## Used by

- [AML.E0043 - UNC5673](../../Entities/AML.E0043%20-%20UNC5673.md) — [UNC5673](../../Entities/AML.E0043%20-%20UNC5673.md) used [Claude Relay Service](AML.S0032%20-%20Claude%20Relay%20Service.md) to aggregate multiple Gemini, Claude, and OpenAI accounts, enabling account pooling and cost-sharing for access to AI services. [gtig-may](https://cloud.google.com/blog/topics/threat-intelligence/ai-vulnerability-exploitation-initial-access)

## Techniques implemented

- [AML.T0008.005 - AI Service Proxies](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md) — [Claude Relay Service](AML.S0032%20-%20Claude%20Relay%20Service.md) provides a self-hosted intermediary between AI clients and upstream model services. It authenticates clients with locally issued API keys and routes their requests through managed upstream account pools, supporting shared access and automatic account switching. [source-1](https://github.com/Wei-Shaw/claude-relay-service)
- [AML.T0141 - AI Service Request Metadata Sanitization](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0141%20-%20AI%20Service%20Request%20Metadata%20Sanitization/README.md) — [Claude Relay Service](AML.S0032%20-%20Claude%20Relay%20Service.md) filters request headers before forwarding them upstream. Its OpenAI filtering removes client-IP, forwarding, and Cloudflare headers, while its Claude filtering forwards only an explicit allowlist. This suppresses metadata that could identify the originating client or intermediary infrastructure. [source-2](https://github.com/Wei-Shaw/claude-relay-service/blob/cf95ecc5e0ba846faaf1b11de574367de89fd00c/src/utils/headerFilter.js)

## References

- [Claude Relay Service GitHub](https://github.com/Wei-Shaw/claude-relay-service)
- [Claude Relay Service header filtering implementation](https://github.com/Wei-Shaw/claude-relay-service/blob/cf95ecc5e0ba846faaf1b11de574367de89fd00c/src/utils/headerFilter.js)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0032)
