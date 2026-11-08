# AML.CS0067 - Claude Code GitHub Action Secret Exposure

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

The [Microsoft Defender Security Research Team](https://www.microsoft.com/en-us/security/blog/author/windows-defender-research/) demonstrated that Anthropic's [Claude Code GitHub Action](https://github.com/anthropics/claude-code-action) could expose CI/CD workflow secrets when processing GitHub content, such as issue bodies, pull request descriptions, and comments, containing prompt injections.

The researchers analyzed the Claude Code Action codebase and obfuscated Claude Agent SDK to understand how agent tools executed and how GitHub events supplied content to the agent. They crafted a prompt framed as a compliance review that directed Claude to read a credential from its process environment, remove the credential prefix, and emit the transformed value. They introduced the prompt through attacker-controlled GitHub content processed by the lab workflow. The action fetched the malicious content into Claude's context, where it was interpreted as instructions.

Claude invoked its Read tool against `/proc/self/environ`, returning the action process's unsanitized environment, including `ANTHROPIC_API_KEY`. Unlike Bash subprocesses, Read operations did not execute within the Bubblewrap sandbox and scrubbed-environment boundary. Removing the key's `sk-ant-` prefix allowed the output to bypass Claude's refusal behavior and GitHub's secret-pattern detection while remaining reconstructable by the researchers. Microsoft identified WebFetch, Bash, GitHub MCP, and GitHub Actions logs as potential additional exfiltration channels depending on workflow configuration.

Microsoft disclosed the issue to Anthropic through HackerOne on April 29, 2026. Anthropic mitigated the vulnerability in Claude Code 2.1.128 on May 5, 2026, by blocking Read access to sensitive `/proc` files.

**Type**  Exercise

**Target**  Claude Code GitHub Action

**Activity period**  2026-06-05

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0095.000 - Code Repositories](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0095%20-%20Search%20Open%20Websites%20-%20Domains/AML.T0095.000%20-%20Code%20Repositories/README.md)

The researchers analyzed the Claude Code Action codebase and the obfuscated Claude Agent SDK. They used the implementation details to understand how agent tools executed and where security boundaries were applied.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0084.001 - Tool Definitions](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.001%20-%20Tool%20Definitions/README.md)

The researchers identified the tools available to Claude Code Action and compared their execution paths. They determined that Bash subprocesses could run within Bubblewrap with a scrubbed environment, while the built-in Read tool performed direct, in-process file access outside that isolation boundary.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0084.002 - Activation Triggers](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.002%20-%20Activation%20Triggers/README.md)

The researchers identified that Claude Code Action could be triggered by GitHub events involving issues, pull requests, and comments and that the action would fetch the associated content into Claude's context.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers crafted a prompt tailored to Claude Code Action framed as a compliance task that directed Claude to read a credential from its environment and emit it.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researchers introduced the malicious prompt through attacker-controlled GitHub content processed by the lab workflow, modeling delivery through an issue body, pull request description, or comment handled by Claude Code Action.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

Claude Code Action incorporated the malicious GitHub content into the model context. Claude interpreted the malicious content as instructions and followed the supplied instructions.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0054 - LLM Jailbreak](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0054%20-%20LLM%20Jailbreak/README.md)

The prompt used benign compliance review framing and instructions to remove the credential prefix to bypass Claude's refusal behavior for emitting a recognizable API key.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

Claude invoked its built-in Read tool on `/proc/self/environ`. Read did not execute within the Bubblewrap and scrubbed-environment boundary applied to Bash subprocesses.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0098 - AI Agent Tool Credential Harvesting](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0098%20-%20AI%20Agent%20Tool%20Credential%20Harvesting/README.md)

The Read tool returned the action process's unsanitized environment, including `ANTHROPIC_API_KEY` and potentially other credentials available to the workflow.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.002 - Conversation Context and Memory](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.002%20-%20Conversation%20Context%20and%20Memory/README.md)

Claude emitted the Anthropic API key after removing its `sk-ant-` prefix. The transformation prevented GitHub's secret scanner from recognizing the credential, while the researchers could reconstruct the original key by restoring the prefix.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

The researchers could use WebFetch, Bash, GitHub MCP, and Action logs as potential exfiltration channels depending on the tools available in the workflow configuration.

**Next**  End of path

## Attributed to

- [AML.E0031 - Microsoft Defender Security Research Team](../../Entities/AML.E0031%20-%20Microsoft%20Defender%20Security%20Research%20Team.md) (Security Evaluation)

## References

- [Securing CI/CD in an agentic world: Claude Code Github action case](https://www.microsoft.com/en-us/security/blog/2026/06/05/securing-ci-cd-in-agentic-world-claude-code-github-action-case/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0067)
