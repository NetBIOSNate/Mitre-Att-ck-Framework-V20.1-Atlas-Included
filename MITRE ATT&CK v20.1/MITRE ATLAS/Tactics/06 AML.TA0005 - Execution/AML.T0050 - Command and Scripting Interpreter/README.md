# AML.T0050 - Command and Scripting Interpreter

[MITRE ATLAS](../../../README.md) / [AML.TA0005 - Execution](../README.md)

Adversaries may abuse command and script interpreters to execute commands, scripts, or binaries. These interfaces and languages provide ways of interacting with computer systems and are a common feature across many different platforms. Most systems come with some built-in command-line interface and scripting capabilities, for example, macOS and Linux distributions include some flavor of Unix Shell while Windows installations include the Windows Command Shell and PowerShell.

There are also cross-platform interpreters such as Python, as well as those commonly associated with client applications such as JavaScript and Visual Basic.

Adversaries may abuse these technologies in various ways as a means of executing arbitrary commands. Commands and scripts can be embedded in Initial Access payloads delivered to victims as lure documents or as secondary payloads downloaded from an existing C2. Adversaries may also execute commands through interactive terminals/shells, as well as utilize various Remote Services in order to achieve remote Execution.

**Tactics**  [AML.TA0005 - Execution](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1059](../../../../Enterprise/Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md) · [MITRE ATT&CK T1059](https://attack.mitre.org/techniques/T1059/)

## Case studies

- [AML.CS0050 - OpenClaw 1-Click Remote Code Execution](../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md#step-s08)
- [AML.CS0052 - LLMSmith: RCE Vulnerabilities in LLM-Integrated Applications](../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md#step-s08)
- [AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md#step-s06)
- [AML.CS0061 - AI in the Middle: Web-Based AI Services as C2 Relays](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md#step-s09)
- [AML.CS0062 - RCE Vulnerability in Semantic Kernel Search Plugin](../../../Case%20Studies/Exercises/AML.CS0062%20-%20RCE%20Vulnerability%20in%20Semantic%20Kernel%20Search%20Plugin.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0062%20-%20RCE%20Vulnerability%20in%20Semantic%20Kernel%20Search%20Plugin.md#step-s04)
- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S09](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s09), [S24](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s24)
- [AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md) · [S15](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s15)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S18](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s18), [S22](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s22), [S34](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s34)

## Mitigations

- [AML.M0011 - Restrict Library Loading](../../../Mitigations/AML.M0011%20-%20Restrict%20Library%20Loading.md) — Restrict library loading so command and script interpreters cannot load untrusted libraries as an execution mechanism.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0050)
