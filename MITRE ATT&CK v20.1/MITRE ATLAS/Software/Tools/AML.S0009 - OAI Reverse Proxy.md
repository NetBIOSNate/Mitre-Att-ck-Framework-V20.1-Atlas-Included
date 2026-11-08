# AML.S0009 - OAI Reverse Proxy

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[OAI Reverse Proxy](AML.S0009%20-%20OAI%20Reverse%20Proxy.md) is an open-source reverse proxy for AI services. It centralizes access to multiple upstream accounts and forwards model requests without exposing the underlying credentials to downstream users. It also checks account configuration and excludes AWS credentials with model-invocation logging enabled. [llmjacking](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/) [canonical-source](https://gitgud.io/khanon/oai-reverse-proxy)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.CS0030 - LLMjacking: Stolen Cloud Credentials Used to Access Cloud LLM Services.](../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md) — The adversaries attempted to access cloud-hosted models using stolen credentials with a user-agent matching [OAI Reverse Proxy](AML.S0009%20-%20OAI%20Reverse%20Proxy.md). [ref-1](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)
- [AML.E0027 - Storm-2139](../../Entities/AML.E0027%20-%20Storm-2139.md) — [Storm-2139](../../Entities/AML.E0027%20-%20Storm-2139.md) staged and operated [OAI Reverse Proxy](AML.S0009%20-%20OAI%20Reverse%20Proxy.md) infrastructure to mediate access to stolen AI service resources. [group-profile](https://blogs.microsoft.com/on-the-issues/2025/02/27/disrupting-cybercrime-abusing-gen-ai/)

## Techniques implemented

- [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md) — [OAI Reverse Proxy](AML.S0009%20-%20OAI%20Reverse%20Proxy.md) forwards requests to AI services using configured account credentials while withholding those credentials from downstream users. During LLMjacking activity, requests bearing its user-agent attempted to access models with compromised cloud credentials. [llmjacking](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)

## References

- [LLMjacking: Stolen Cloud Credentials Used in New AI Attack](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)
- [OAI Reverse Proxy: canonical implementation source](https://gitgud.io/khanon/oai-reverse-proxy)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0009)
