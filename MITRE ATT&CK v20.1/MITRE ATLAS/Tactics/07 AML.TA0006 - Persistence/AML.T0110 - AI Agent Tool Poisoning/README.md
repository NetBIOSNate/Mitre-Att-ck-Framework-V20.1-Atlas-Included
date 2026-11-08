# AML.T0110 - AI Agent Tool Poisoning

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may poison tools used by AI agents by introducing or modifying malicious content or behavior in a tool's model-visible definition, executable implementation, or runtime responses. Tools may include built-in integrations, locally installed packages, remotely hosted services, Model Context Protocol (MCP) servers and tools, and agent skills or similar capability packages.

A poisoned tool is represented or trusted as performing a benign function, but its definition, implementation, or responses cause agent behavior or tool-mediated effects to differ materially from the represented function. Poisoning may be present when a tool is first published, introduced through a [Supply Chain Compromise](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md), or added after adoption through an [AI Supply Chain Rug Pull](../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0109%20-%20AI%20Supply%20Chain%20Rug%20Pull/README.md). Once the tool is installed, connected, or otherwise made available to the agent, it may provide the adversary with persistent influence over the agent's actions and external interactions.

Adversaries may poison a tool's model-visible semantic interface, including its descriptions, schemas, parameter documentation, annotations, or agent-readable instructions (See [Definition and Instructions](AML.T0110.000%20-%20Definition%20and%20Instructions/README.md)). They may introduce hidden executable behavior that changes the effects of otherwise normal tool invocations (See [Implementation](AML.T0110.001%20-%20Implementation/README.md)). They may also cause a malicious or compromised tool to deliberately return content intended to influence the model's subsequent reasoning or actions (See [Runtime Response](AML.T0110.002%20-%20Runtime%20Response/README.md)).

Poisoned tools may cause an agent to access sensitive data, alter the inputs or destinations of other tools, execute unauthorized commands, conceal actions from users, or exfiltrate information. Tool poisoning frequently enables other techniques such as [LLM Prompt Injection](../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md), [AI Agent Tool Invocation](../../06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md), and [Exfiltration via AI Agent Tool Invocation](../../15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md).

Tool poisoning is distinct from malicious data that a benign tool faithfully retrieves from an external or victim-controlled source (See [AI Agent Tool Data Poisoning](../AML.T0099%20-%20AI%20Agent%20Tool%20Data%20Poisoning/README.md) and [LLM Prompt Injection: Indirect](../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md). Software that merely uses an agent tool package as a delivery vehicle for conventional malware, without subverting the tool's represented interface or operation, may be better described as a malicious package or software supply-chain compromise rather than AI Agent Tool Poisoning.

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0110.000 - Definition and Instructions](AML.T0110.000%20-%20Definition%20and%20Instructions/README.md)
- [AML.T0110.001 - Implementation](AML.T0110.001%20-%20Implementation/README.md)
- [AML.T0110.002 - Runtime Response](AML.T0110.002%20-%20Runtime%20Response/README.md)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0110)
