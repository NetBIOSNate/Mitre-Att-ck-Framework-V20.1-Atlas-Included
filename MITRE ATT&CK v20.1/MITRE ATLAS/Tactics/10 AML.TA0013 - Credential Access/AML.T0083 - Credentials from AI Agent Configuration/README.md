# AML.T0083 - Credentials from AI Agent Configuration

[MITRE ATLAS](../../../README.md) / [AML.TA0013 - Credential Access](../README.md)

Adversaries may access the credentials of other tools or services on a system from the configuration of an AI agent.

AI Agents often utilize external tools or services to take actions, such as querying databases, invoking APIs, or interacting with cloud resources. To enable these functions, credentials like API keys, tokens, and connection strings are frequently stored in configuration files. While there are secure methods such as dedicated secret managers or encrypted vaults that can be deployed to store and manage these credentials, in practice they are often placed in less protected locations for convenience or ease of deployment. If an attacker can read or extract these configurations, they may obtain valid credentials that allow direct access to sensitive systems outside the agent itself.

**Tactics**  [AML.TA0013 - Credential Access](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0045 - Data Exfiltration via an MCP Server used by Cursor](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md#step-s08)
- [AML.CS0048 - Exposed ClawdBot Control Interfaces Leads to Credential Access and Execution](../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md#step-s02)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0083)
