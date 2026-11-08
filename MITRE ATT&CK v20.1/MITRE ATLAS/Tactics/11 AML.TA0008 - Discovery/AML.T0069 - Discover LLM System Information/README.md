# AML.T0069 - Discover LLM System Information

[MITRE ATLAS](../../../README.md) / [AML.TA0008 - Discovery](../README.md)

The adversary is trying to discover something about the large language model's (LLM) system information. This may be found in a configuration file containing the system instructions or extracted via interactions with the LLM. The desired information may include the full system prompt, special characters that have significance to the LLM or keywords indicating functionality available to the LLM. Information about how the LLM is instructed can be used by the adversary to understand the system's capabilities and to aid them in crafting malicious prompts.

**Tactics**  [AML.TA0008 - Discovery](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Sub-techniques

- [AML.T0069.000 - Special Character Sets](AML.T0069.000%20-%20Special%20Character%20Sets/README.md)
- [AML.T0069.001 - System Instruction Keywords](AML.T0069.001%20-%20System%20Instruction%20Keywords/README.md)
- [AML.T0069.002 - System Prompt](AML.T0069.002%20-%20System%20Prompt/README.md)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Withhold public prompt templates, model configuration, and architecture details that could aid LLM reconnaissance.
- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Restrict access to stored system prompts, configuration files, and model metadata.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Authenticate and monitor access to production models and configuration interfaces.
- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect responses for disclosure of nonpublic system instructions, internal configuration, and implementation details. Block or redact information that the requesting user is not authorized to receive.

## Software implementations

- [AML.S0008 - keychecker](../../../Software/Tools/AML.S0008%20-%20keychecker.md) — [keychecker](../../../Software/Tools/AML.S0008%20-%20keychecker.md) probes AI services with supplied credentials to identify accessible models and account capabilities. Its provider specific checks retrieve information such as enabled models, quotas, permissions, billing status, and model invocation logging configuration. [github](https://github.com/cunnymessiah/keychecker) [llmjacking](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0069)
