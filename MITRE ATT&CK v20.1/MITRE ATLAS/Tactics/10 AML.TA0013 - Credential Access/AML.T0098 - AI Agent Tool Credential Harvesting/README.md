# AML.T0098 - AI Agent Tool Credential Harvesting

[MITRE ATLAS](../../../README.md) / [AML.TA0013 - Credential Access](../README.md)

Adversaries may attempt to use their access to an AI agent on the victim's system to retrieve data from available agent tools to collect credentials. Agent tools may connect to a wide range of sources that may contain credentials including document stores (e.g. SharePoint, OneDrive or Google Drive), code repositories (e.g. GitHub or GitLab), or enterprise productivity tools (e.g. as email providers or Slack), and local notetaking tools (e.g. Obsidian or Apple Notes).

**Tactics**  [AML.TA0013 - Credential Access](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0048 - Exposed ClawdBot Control Interfaces Leads to Credential Access and Execution](../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md#step-s05)
- [AML.CS0054 - Data Exfiltration via Remote Poisoned MCP Tool](../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md#step-s08)
- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s08)

## Mitigations

- [AML.M0032 - Segmentation of AI Agent Components](../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to harvest credentials.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0098)
