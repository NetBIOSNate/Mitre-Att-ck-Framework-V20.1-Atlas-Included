# AML.M0030 - Restrict AI Agent Tool Invocation on Untrusted Data

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Untrusted data can contain prompt injections that invoke an AI agent's tools, potentially causing confidentiality, integrity or availability violations. It is recommended that tool invocation be restricted or limited when untrusted data enters the LLM's context.

The degree to which tool invocation is restricted may depend on the potential consequences of the action. Consider blocking the automatic invocation of tools or requiring user confirmation once untrusted data enters the LLM's context. For high consequence actions, consider always requiring user confirmation.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Deployment

## Techniques mitigated

- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Restricting the automatic tool use when untrusted data is present can prevent adversaries from invoking tools via prompt injections.
- [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Restricting the automatic tool use when untrusted data is present can prevent adversaries from invoking tools via prompt injections.
- [AML.T0101 - Data Destruction via AI Agent Tool Invocation](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0101%20-%20Data%20Destruction%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Restricting the automatic tool use when untrusted data is present can prevent adversaries from invoking tools via prompt injections.
- [AML.T0143 - LLM Prompt Propagation](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md) — Restrict tool actions that send messages, publish content, modify shared resources, or communicate with other agents when untrusted content has entered the agent's context. Apply these restrictions to delayed actions and derived content that retain the influence of the untrusted instructions.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0030)
