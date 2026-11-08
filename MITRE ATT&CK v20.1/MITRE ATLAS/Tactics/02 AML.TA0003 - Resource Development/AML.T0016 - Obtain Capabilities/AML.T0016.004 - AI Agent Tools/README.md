# AML.T0016.004 - AI Agent Tools

[MITRE ATLAS](../../../../README.md) / [AML.TA0003 - Resource Development](../../README.md) / [AML.T0016 - Obtain Capabilities](../README.md)

Adversaries may search for and obtain tools that extend the capabilities of an AI agent. These capabilities may allow an agent to interact with operating systems, browsers, networks, cloud services, data stores, software repositories, identity systems, or other external resources.

AI agent tools may be distributed as Model Context Protocol servers, plugins, skills, connectors, function libraries, computer-use adapters, execution brokers, remote APIs, or similar integrations. Adversaries may obtain legitimate tools and configure them for malicious use, acquire modified or purpose-built tools, or combine multiple integrations into an operational toolset.

Agent tools may expose model-visible descriptions and executable interfaces that influence which capabilities an agent selects and how it invokes them. Obtaining these tools may give an agent access to resources, credentials, or actions that are unavailable through model inference alone.

**Tactics**  [AML.TA0003 - Resource Development](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md), [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S02](../../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s02)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0016.004)
