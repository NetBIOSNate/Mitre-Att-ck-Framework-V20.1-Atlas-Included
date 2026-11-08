# AML.CS0052 - LLMSmith: RCE Vulnerabilities in LLM-Integrated Applications

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers identified 20 remote code execution (RCE) vulnerabilities across 11 different LLM frameworks. They discovered applications deployed on the public internet built using these LLM frameworks and demonstrated the RCE vulnerabilities could be exploited using prompt injection.

The 11 LLM frameworks the researchers evaluated were: LangChain, LlamaIndex, Pandas-ai, Langflow, Pandas-llm, Auto-GPT, Griptape, Lagent, MetaGPT, vanna,  and langroid.

**Type**  Exercise

**Actor**  Researchers at University of Chinese Academy of Sciences, Shandong University, and University of New South Wales

**Target**  LLM Integration Frameworks

**Activity period**  2025-02-27

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017 - Develop Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/README.md)

The researchers performed a static analysis on the APIs of target LLM frameworks to identify functions that execute code from either user input or the response from an LLM and are thus vulnerable to RCE.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0004 - Search Application Repositories](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0004%20-%20Search%20Application%20Repositories/README.md)

The researchers performed targeting to identify applications that are likely built with LLM Frameworks and may use the functions vulnerable to RCE. This was done by scanning source code repositories for app deployment URLs.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0084.003 - Call Chains](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.003%20-%20Call%20Chains/README.md)

The researchers ran their static analysis to extract call chains from target application's source code to identify those that utilize LLM framework functions vulnerable to RCE.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers developed prompts to trigger tool invocations that lead to RCE.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

The researchers targeted public-facing applications that expose an AI agent to user input as a means to execute their prompts.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.000 - Direct](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.000%20-%20Direct/README.md)

The researchers directly prompted the AI agent with their malicious instructions.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0054 - LLM Jailbreak](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0054%20-%20LLM%20Jailbreak/README.md)

For target applications where the AI agent refused the researcher's request, they used lightweight jailbreaking strategies to bypass the LLM's guardrails.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The researchers' prompts called the AI agent's tools, targeting call chains that can lead to code execution.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0050 - Command and Scripting Interpreter](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0050%20-%20Command%20and%20Scripting%20Interpreter/README.md)

The code included in the researcher's prompts was executed in a sandboxed Python interpreter.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0105 - Escape to Host](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0105%20-%20Escape%20to%20Host/README.md)

The researchers included code escape techniques designed to bypass any limitations a sandbox may place on code execution.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0014 - Command and Control](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/README.md) / [AML.T0072 - Cyber Communication Channel](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0072%20-%20Cyber%20Communication%20Channel/README.md)

The Python code opened a reverse shell which was used as a command and control channel.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0112.000 - Local AI Agent](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0112%20-%20Machine%20Compromise/AML.T0112.000%20-%20Local%20AI%20Agent/README.md)

The researchers gained full control of the system running the LLM-integrated application.

**Next**  End of path

## References

- [Demystifying RCE Vulnerabilities in LLM-Integrated Apps](https://arxiv.org/abs/2309.02926)
- [LLMSmith Website](https://sites.google.com/view/llmsmith)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0052)
