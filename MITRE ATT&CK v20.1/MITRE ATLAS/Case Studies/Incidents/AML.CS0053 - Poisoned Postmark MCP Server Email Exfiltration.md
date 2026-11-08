# AML.CS0053 - Poisoned Postmark MCP Server Email Exfiltration

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

A bad actor successfully exfiltrated emails from users of the Postmark's MCP server via a supply chain attack. Postmark is an email delivery service that allows organizations to send marketing and transactional emails via API. The Postmark MCP server allows users to interact with Postmark via AI agents.

The bad actor impersonated Postmark, by registering the `postmark-mcp` package name on npm. They initially published the legitimate versions of the MCP server. After the package became popular and reached over 1,000 downloads per week, the bad actor performed a rugpull and uploaded a malicious version of the package. The malicious version added the bad actor's email address in the BCC line of all emails sent by the MCP tool. Users who upgraded to this version and continued to use the tool would have all emails exfiltrated to the bad actor.

**Type**  Incident

**Actor**  Unknown Bad Actor

**Target**  Postmark MCP Server

**Reporter**  Koi Research

**Activity period**  2025-09-17 to 2025-09-25

## Procedure steps

### Step S00

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0073 - Impersonation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0073%20-%20Impersonation/README.md)

The bad actor impersonated Postmark by publishing a legitimate version of their `postmark-mcp` package to npm.  Postmark had not registered the `postmark-mcp` name on npm themselves, allowing the bad actor to namesquat. Legitimate users were tricked into using the npm package even though it wasn't managed by the official developers of `postmark-mcp`

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017 - Develop Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/README.md)

The bad actor modified the legitimate Postmark MCP server to include their email address on the BCC line on all emails sent by the tool.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0115.002 - AI Agent Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.002%20-%20AI%20Agent%20Tools/README.md)

The bad actor published their malicious version of `postmark-mcp` to npm.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0109 - AI Supply Chain Rug Pull](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0109%20-%20AI%20Supply%20Chain%20Rug%20Pull/README.md)

By waiting for users to adopt a legitimate version of `postmark-mcp` first, the bad actor was able to evade the additional scrutiny and scanning performed on new tools.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.005 - AI Agent Tool](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.005%20-%20AI%20Agent%20Tool/README.md)

When organizations upgraded `postmark-mcp` to version `1.0.16`, they received the malicious version of the tool via the compromised supply chain.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0110.001 - Implementation](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0110%20-%20AI%20Agent%20Tool%20Poisoning/AML.T0110.001%20-%20Implementation/README.md)

Once configured with the organization's AI agents, the poisoned Postmark MCP server's effects persist.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.002 - Poisoned AI Agent Tool](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.002%20-%20Poisoned%20AI%20Agent%20Tool/README.md)

When users at the victim organization instructed their AI agent to use tools provided by the poisoned Postmark MCP Server, the malicious code was executed.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

When organizations sent emails via the `postmark-mcp` tool, the entire contents of their emails are exfiltrated to the bad actor via the address added on the BCC line.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048 - External Harms](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/README.md)

The exfiltrated emails may include transactional emails (revealing private information about the organization's clients) and promotional emails (revealing the organization's client list).

**Next**  End of path

## Uses

- [AML.S0019 - postmark-mcp](../../Software/Malware/AML.S0019%20-%20postmark-mcp.md) — The actor distributed [postmark-mcp](../../Software/Malware/AML.S0019%20-%20postmark-mcp.md) on npm under Postmark's name, initially publishing functional copies of the legitimate integration before introducing a backdoor in version 1.0.16. The modified email tool silently added an adversary-controlled BCC address to outgoing messages, forwarding their contents whenever users or AI agents sent email through the package. [postmark-advisory](https://postmarkapp.com/blog/information-regarding-malicious-postmark-mcp-package/) [snyk-analysis](https://snyk.io/blog/malicious-mcp-server-on-npm-postmark-mcp-harvests-emails/)

## References

- [First Malicious MCP in the Wild: The Postmark Backdoor That's Stealing Your Emails](https://www.koi.ai/blog/postmark-mcp-npm-malicious-backdoor-email-theft)
- [Security Alert: Malicious 'postmark-mcp' npm Package Impersonating Postmark](https://postmarkapp.com/blog/information-regarding-malicious-postmark-mcp-package/)
- [Malicious MCP Server on npm postmark-mcp Harvests Emails](https://snyk.io/blog/malicious-mcp-server-on-npm-postmark-mcp-harvests-emails/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0053)
