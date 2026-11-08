# AML.S0008 - keychecker

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[keychecker](AML.S0008%20-%20keychecker.md) is an open-source Python command-line utility for bulk validation of credentials across AI services. Depending on the provider, it reports accessible models, usage quotas, rate limits, account balances, subscription or billing status, permissions, and logging configuration. It supports reading credentials from files or standard input and exporting results in a format compatible with OAI Reverse Proxy. [github](https://github.com/cunnymessiah/keychecker)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.CS0030 - LLMjacking: Stolen Cloud Credentials Used to Access Cloud LLM Services.](../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md) — The adversaries used [keychecker](AML.S0008%20-%20keychecker.md) to test stolen credentials for access to cloud-hosted AI services and identify available models and quotas. They also queried logging settings where supported to assess whether subsequent model use would be recorded. [ref-1](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)

## Techniques implemented

- [AML.T0069 - Discover LLM System Information](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/README.md) — [keychecker](AML.S0008%20-%20keychecker.md) probes AI services with supplied credentials to identify accessible models and account capabilities. Its provider specific checks retrieve information such as enabled models, quotas, permissions, billing status, and model invocation logging configuration. [github](https://github.com/cunnymessiah/keychecker) [llmjacking](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)

## References

- [LLMjacking: Stolen Cloud Credentials Used in New AI Attack](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)
- [keychecker GitHub](https://github.com/cunnymessiah/keychecker)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0008)
