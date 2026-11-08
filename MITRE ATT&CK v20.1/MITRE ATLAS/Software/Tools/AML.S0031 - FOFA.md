# AML.S0031 - FOFA

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[FOFA](AML.S0031%20-%20FOFA.md) is an internet asset-search service operated by Hunan HuaShun Xin'an Technology Co., Ltd. It actively discovers internet-facing systems and indexes fingerprints identifying exposed software, hardware, and services. Its search interface and API support asset discovery, host-level lookups, and aggregated analysis of matching infrastructure. [product-overview](https://en.fofa.info/about/en) [source-1](https://en.fofa.info/api)

**Software type**  Tool

**Software categories**  service

## Used by

- [AML.E0038 - knaithe](../../Entities/AML.E0038%20-%20knaithe.md) — [knaithe](../../Entities/AML.E0038%20-%20knaithe.md) used [FOFA](AML.S0031%20-%20FOFA.md) through scripts and an MCP integration to identify internet-exposed services. Their autonomous agent enumerated Langflow instances, compared deployment counts across alternative product families, and narrowed searches to Chinese n8n instances for version checks and exploitation attempts. [unit42](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

## Techniques implemented

- [AML.T0000.003 - Scan Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/AML.T0000.003%20-%20Scan%20Databases/README.md) — [FOFA](AML.S0031%20-%20FOFA.md) makes internet-scan results searchable through a web interface and API. Users can query indexed service fingerprints and HTTP content to identify exposed AI applications and supporting infrastructure, retrieve candidate hosts, and compare deployment counts without directly probing each target. [product-overview](https://en.fofa.info/about/en) [source-1](https://en.fofa.info/api)

## References

- [FOFA API documentation](https://en.fofa.info/api)
- [About FOFA](https://en.fofa.info/about/en)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0031)
