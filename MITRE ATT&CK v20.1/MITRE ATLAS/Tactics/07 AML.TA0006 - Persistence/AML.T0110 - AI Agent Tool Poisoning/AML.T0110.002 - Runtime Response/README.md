# AML.T0110.002 - Runtime Response

[MITRE ATLAS](../../../../README.md) / [AML.TA0006 - Persistence](../../README.md) / [AML.T0110 - AI Agent Tool Poisoning](../README.md)

Adversaries may poison the runtime response channel of a malicious or compromised AI agent tool by deliberately returning content intended to influence the model's subsequent reasoning, decisions, or actions. Poisoned responses may contain malicious instructions, deceptive data, fabricated errors, embedded resources, or other content designed to be treated as trusted context after an approved tool invocation.

Because tool responses are commonly incorporated into the model's context, an adversary may use them to direct the agent to invoke additional tools, access sensitive information, alter an ongoing workflow, or transmit data to an adversary-controlled destination. Poisoned instructions may be mixed with legitimate results so that the tool appears to operate normally. Responses may use structured or unstructured content, including text, images, resource links, embedded resources, or schema-conforming fields  [mcp-tools](https://modelcontextprotocol.io/specification/2025-11-25/server/tools) [owasp-tool-poisoning](https://owasp.org/www-community/attacks/MCP_Tool_Poisoning).

**Tactics**  [AML.TA0006 - Persistence](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Validate tool responses before incorporating them into model context. Detect malicious instructions, fabricated errors, embedded resources, or other content that instructs the agent, and check subsequent actions.

## References

- [Model Context Protocol Specification: Tools](https://modelcontextprotocol.io/specification/2025-11-25/server/tools)
- [MCP Tool Poisoning](https://owasp.org/www-community/attacks/MCP_Tool_Poisoning)
- [MCP Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/MCP_Security_Cheat_Sheet.html)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0110.002)
