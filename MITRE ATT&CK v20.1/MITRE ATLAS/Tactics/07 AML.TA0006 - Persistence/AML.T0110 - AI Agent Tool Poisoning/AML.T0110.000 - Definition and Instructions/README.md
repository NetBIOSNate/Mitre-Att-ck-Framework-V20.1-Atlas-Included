# AML.T0110.000 - Definition and Instructions

[MITRE ATLAS](../../../../README.md) / [AML.TA0006 - Persistence](../../README.md) / [AML.T0110 - AI Agent Tool Poisoning](../README.md)

Adversaries may poison the model-visible definition or operational instructions of an AI agent tool to manipulate how an agent interprets, selects, or invokes the tool. The poisoned content may be contained in tool descriptions, docstrings, parameter names, help text, input or output schemas, annotations, examples, manifests, skill instruction files, or other static content used to explain a tool's capabilities to the model.

Malicious instructions in this layer may direct the agent to collect additional data, populate hidden or unnecessary parameters, conceal actions from the user, or invoke other tools. Because an agent may receive a more complete representation of a tool than is shown in the user interface, the model may process malicious instructions that are invisible or only partially visible to a human reviewer [invariant-tool-poisoning](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks).

Definition poisoning may also be used for tool shadowing, in which the definition of one malicious tool contains instructions that alter how the agent selects or invokes another trusted tool. The poisoned tool may not need to be invoked for its definition to influence the agent if definitions from multiple connected tools are included in the same model context [invariant-tool-poisoning](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks).

**Tactics**  [AML.TA0006 - Persistence](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0049 - Supply Chain Compromise via Poisoned ClawdBot Skill](../../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md#step-s06)
- [AML.CS0054 - Data Exfiltration via Remote Poisoned MCP Tool](../../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md#step-s03)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect tool descriptions, schemas, examples, and operational instructions before exposing them to the model. Reject content that directs unrelated data collection, concealed actions, or manipulation of other tools, and independently validate resulting tool requests.

## References

- [MCP Security Notification: Tool Poisoning Attacks](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks)
- [Model Context Protocol Specification: Tools](https://modelcontextprotocol.io/specification/2025-06-18/server/tools)
- [MCP Tool Poisoning](https://owasp.org/www-community/attacks/MCP_Tool_Poisoning)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0110.000)
