# AML.M0033 - Input and Output Validation for AI Agent Components

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Implement validation on inputs and outputs for the tools and data sources used by AI agents. Validation includes enforcing a common data format, schema validation, checks for sensitive or prohibited information leakage, and data sanitization to remove potential injections or unsafe code. Input and output validation can help prevent compromises from spreading in AI-enabled systems and can help secure the workflow when multiple components are chained together. Validation should be performed external to the AI agent.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Business and Data Understanding, Data Preparation, Deployment

## Techniques mitigated

- [AML.T0051 - LLM Prompt Injection](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md) — Validation can prevent adversaries from executing prompt injections that could affect agentic workflows.
- [AML.T0051.000 - Direct](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.000%20-%20Direct/README.md) — Validation can prevent adversaries from executing prompt injections that could affect agentic workflows.
- [AML.T0051.001 - Indirect](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md) — Validation can prevent adversaries from executing prompt injections that could affect agentic workflows.
- [AML.T0051.002 - Triggered](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.002%20-%20Triggered/README.md) — Validation can prevent adversaries from executing prompt injections that could affect agentic workflows.
- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Validation can prevent adversaries from utilizing tools in an agentic workflow to generate unsafe output.
- [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Validation can prevent adversaries from utilizing tools in an agentic workflow to compromise sensitive data sources.
- [AML.T0143 - LLM Prompt Propagation](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md) — Validate content before it is forwarded, published, synchronized, or written to resources used by other AI components. Inspect messages, shared documents, agent instructions, rules files, and templates for embedded malicious instructions, including hidden or encoded content. Perform validation outside the agent and at receiving boundaries before accepting transferred content.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0033)
