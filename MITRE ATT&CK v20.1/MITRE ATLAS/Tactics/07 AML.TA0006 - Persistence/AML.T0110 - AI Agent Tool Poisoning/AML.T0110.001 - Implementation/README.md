# AML.T0110.001 - Implementation

[MITRE ATLAS](../../../../README.md) / [AML.TA0006 - Persistence](../../README.md) / [AML.T0110 - AI Agent Tool Poisoning](../README.md)

Adversaries may poison the executable implementation of an AI agent tool so that normal tool invocation produces unauthorized behavior or hidden side effects. The tool may continue to provide its represented functionality while also accessing additional data, modifying requests, changing recipients or destinations, executing unauthorized commands, weakening security controls, or performing covert data exfiltration.

Implementation poisoning does not require the model to interpret or follow malicious instructions. The adversarial effect is produced by executable logic when the agent or user invokes the tool. For example, a poisoned email tool may send the requested message while silently adding an adversary-controlled blind-copy recipient. A file-processing tool may return the requested result while also transmitting the source file to an external service.

Implementation poisoning may be introduced before publication, through compromise of a tool's source repository or build process, or through a malicious update after users have adopted a benign version. Installed copies may continue to exhibit the poisoned behavior even after the malicious package or remote listing is removed [koi-postmark](https://www.koi.ai/blog/postmark-mcp-npm-malicious-backdoor-email-theft).

**Tactics**  [AML.TA0006 - Persistence](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0053 - Poisoned Postmark MCP Server Email Exfiltration](../../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md) · [S05](../../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md#step-s05)

## References

- [First Malicious MCP in the Wild: The Postmark Backdoor That's Stealing Your Emails](https://www.koi.ai/blog/postmark-mcp-npm-malicious-backdoor-email-theft)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0110.001)
