# AML.S0036 - CLIProxyAPI

[MITRE ATLAS](../../README.md) / [Software](../README.md)

CLIProxyAPI is an open source proxy server that provides compatible API interfaces for accessing multiple AI services through a common gateway. It supports OAuth authentication, multiple accounts with load balancing, streaming responses, tool calling, and multimodal inputs. Applications can use clients compatible with OpenAI, Gemini, or Claude to access supported upstream services. [github](https://github.com/router-for-me/CLIProxyAPI)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.E0043 - UNC5673](../../Entities/AML.E0043%20-%20UNC5673.md) — [UNC5673](../../Entities/AML.E0043%20-%20UNC5673.md) used [CLIProxyAPI](AML.S0036%20-%20CLIProxyAPI.md) to provide compatible API interfaces for multiple AI models and support account pooling across AI services. [gtig-may](https://cloud.google.com/blog/topics/threat-intelligence/ai-vulnerability-exploitation-initial-access)

## Techniques implemented

- [AML.T0008.005 - AI Service Proxies](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md) — [CLIProxyAPI](AML.S0036%20-%20CLIProxyAPI.md) exposes compatible API endpoints that relay client requests to upstream AI services using configured accounts and credentials. Its multi-account support distributes requests across account pools through round-robin load balancing, providing shared access through a common proxy. [github](https://github.com/router-for-me/CLIProxyAPI)
- [AML.T0140 - Centralized AI Service Request Routing](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md) — [CLIProxyAPI](AML.S0036%20-%20CLIProxyAPI.md) centrally routes AI service requests across multiple configured upstream accounts using round-robin load balancing. This distributes a client's workload across an account pool while presenting a common API endpoint to the client. [github](https://github.com/router-for-me/CLIProxyAPI)

## References

- [CLIProxyAPI - Official GitHub Repository](https://github.com/router-for-me/CLIProxyAPI)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0036)
