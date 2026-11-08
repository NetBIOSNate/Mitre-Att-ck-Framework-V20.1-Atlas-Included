# AML.T0008.005 - AI Service Proxies

[MITRE ATLAS](../../../../README.md) / [AML.TA0003 - Resource Development](../../README.md) / [AML.T0008 - Acquire Infrastructure](../README.md)

Adversaries may acquire proxy infrastructure that mediates access to AI services. Proxies can provide a common interface to multiple upstream accounts or providers while concealing underlying credentials from downstream users. Adversaries may purchase access to existing proxy services from commercial operators or gray-market resellers, or deploy publicly available proxy software on their own infrastructure.

Proxy infrastructure may route requests across provider APIs, cloud endpoints, aggregators, and account pools based on service health, availability, quotas, or cost, with failover when access is disrupted. [cisa](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a) Operators may rotate or replace accounts and mix coordinated requests with unrelated customer traffic, enabling access from restricted regions as well as complicating detection and attribution (See [Centralized AI Service Request Routing](../../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md)). [anthropic](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks) [chinatalk](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in).Adversaries may deliberately utilize proxies for [Defense Evasion](../../../09%20AML.TA0007%20-%20Defense%20Evasion/README.md) (See [Centralized AI Service Request Routing](../../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md) and [AI Service Request Metadata Sanitization](../../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0141%20-%20AI%20Service%20Request%20Metadata%20Sanitization/README.md)).

AI service proxy infrastructure may be used as "transfer stations" for gray-market resale. Their upstream suppliers may [Establish Accounts](../../AML.T0021%20-%20Establish%20Accounts/README.md) through bulk registration, supported by verification and payment intermediaries, while operators pool capacity from promotional credits, discounted access, unused quotas, or shared subscriptions. [chinatalk](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in) Proxy infrastructure may also use [Valid Accounts]( /techniques/AML.T0012) obtained through credential theft as observed in [LLMjacking]( /studies/AML.CS0030) campaigns. [sysdig](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)

Adversaries have used proxy services to route requests and collect responses for model distillation campaigns. [anthropic](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks) [cisa](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a) Adversaries may collect [Outputs from AI Models](../../../13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md) and use them to [Replicate Behavior from Model Outputs](../../AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md).

**Tactics**  [AML.TA0003 - Resource Development](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0030 - LLMjacking: Stolen Cloud Credentials Used to Access Cloud LLM Services.](../../../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md) · [S07](../../../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md#step-s07)
- [AML.CS0056 - Model Distillation Campaigns Targeting Anthropic Claude](../../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md) · [S00](../../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md#step-s00)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S03](../../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s03)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S02](../../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s02)

## Software implementations

- [AML.S0032 - Claude Relay Service](../../../../Software/Tools/AML.S0032%20-%20Claude%20Relay%20Service.md) — [Claude Relay Service](../../../../Software/Tools/AML.S0032%20-%20Claude%20Relay%20Service.md) provides a self-hosted intermediary between AI clients and upstream model services. It authenticates clients with locally issued API keys and routes their requests through managed upstream account pools, supporting shared access and automatic account switching. [source-1](https://github.com/Wei-Shaw/claude-relay-service)
- [AML.S0036 - CLIProxyAPI](../../../../Software/Tools/AML.S0036%20-%20CLIProxyAPI.md) — [CLIProxyAPI](../../../../Software/Tools/AML.S0036%20-%20CLIProxyAPI.md) exposes compatible API endpoints that relay client requests to upstream AI services using configured accounts and credentials. Its multi-account support distributes requests across account pools through round-robin load balancing, providing shared access through a common proxy. [github](https://github.com/router-for-me/CLIProxyAPI)

## References

- [Detecting and preventing distillation attacks \\ Anthropic](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks)
- [LLMjacking: Stolen Cloud Credentials Used in New AI Attack | Sysdig](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)
- [How to Buy Cheap Claude Tokens in China: The Transfer Station Economy, Explained](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in)
- [Detecting and preventing distillation attacks](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks)
- [China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0008.005)
