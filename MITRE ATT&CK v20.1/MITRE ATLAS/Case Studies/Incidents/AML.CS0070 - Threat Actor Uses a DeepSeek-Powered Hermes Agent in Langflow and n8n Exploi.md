# AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

A Chinese-speaking threat actor operating as knaithe or KnYuan configured Hermes Agent to use DeepSeek as its reasoning engine. Hermes supplied terminal access, Telegram-based operator control, and a skills system containing both bundled and actor-created red-team skills. The actor also integrated an MCP server that exposed FOFA search, query translation, and Nuclei scan-generation capabilities.

Unit 42 recovered a detailed Hermes Agent session dated May 7, 2026. The actor supplied an initial task through Telegram, but Unit 42 recovered no additional operator input during the session. The DeepSeek-powered Hermes Agent then autonomously searched for targets, obtained public exploits, ran scans, evaluated the results, and revised its approach.

The agent initially targeted Langflow using a public exploit for CVE-2026-33017. After determining that available targets lacked the exploit's prerequisites, it abandoned that path, compared vulnerabilities across 10 product families, and selected n8n based on apparent severity, exposure, and exploitability. It then obtained a public exploit chain for CVE-2026-21858 and CVE-2025-68613 and probed candidate systems identified through FOFA. Although several systems appeared to run affected versions, the agent found that they lacked the required unauthenticated file-upload functionality. None of the autonomous exploitation attempts obtained access.

Separate workspace evidence documented manual actor activity involving Citrix NetScaler data extraction, Marimo command execution, and reverse-shell attempts against Tomcat and IKE VPN systems.

Unit 42 obtained this visibility after Hermes Agent responded to a Telegram command by starting an HTTP file server from the actor's home directory, `/home/worker`, instead of an isolated staging directory. This unintentionally exposed the actor's workspace, including AI tool configurations, API keys, exploit scripts, target lists, Bash history, and autonomous exploitation session logs.

**Type**  Incident

**Target**  Publicly exposed Langflow and n8n systems, primarily in China

**Activity period**  2026-05-07

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.002 - Generative AI](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.002%20-%20Generative%20AI/README.md)

The actor obtained access to several generative-AI models and services while evaluating an operational toolset. DeepSeek was selected as the primary reasoning engine for the autonomous attack activity.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.001 - Software Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.001%20-%20Software%20Tools/README.md)

The actor obtained and configured Hermes Agent as the offensive framework, together with scripts and conventional scanning and exploitation utilities. Hermes provided terminal access, Telegram-based operator control, and a skills system.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.004 - AI Agent Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.004%20-%20AI%20Agent%20Tools/README.md)

The actor obtained agent-specific capabilities, including Hermes's framework-bundled godmode skill, which integrated G0DM0D3 and L1B3RT4S jailbreak materials, and the open-source FofaMap MCP server. The MCP server exposed FOFA asset search, natural-language query translation, and Nuclei scan generation to DeepSeek. Unit 42 does not establish that the godmode skill or either prompt package was invoked during the recovered session.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.002 - AI Agent Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.002%20-%20AI%20Agent%20Tools/README.md)

The actor created two Hermes skills. web-terminal-exploitation encoded a procedure for unauthenticated WebSocket exploitation, while fofa-cyberspace-search instructed DeepSeek to use the actor's fofoapi.py script for internet asset enumeration. The observed FOFA workflow is consistent with the latter skill; the report does not attribute an action in the recovered session to web-terminal-exploitation.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0040 - AI Model Inference API Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md)

Hermes accessed DeepSeek through its native API and used the model for vulnerability assessment, target selection, command generation, and operational decisions.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md)

After receiving an initial task, DeepSeek sequenced reconnaissance and exploitation actions, evaluated failed prerequisites, abandoned Langflow, compared alternative products and vulnerabilities, and selected n8n. Unit 42 recovered no additional operator input during the session.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0102 - Generate Malicious Commands](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0102%20-%20Generate%20Malicious%20Commands/README.md)

DeepSeek generated FOFA queries, shell commands, scanner invocations, and direct HTTP probes based on the results returned during the session.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md)

DeepSeek investigated Langflow, determined what information and prerequisites were needed, and selected follow-on reconnaissance based on returned results.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0000.003 - Scan Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/AML.T0000.003%20-%20Scan%20Databases/README.md)

DeepSeek queried FOFA and obtained records for 84 exposed Langflow instances. These were exposure records, not confirmed vulnerable targets.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.003 - Exploits](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.003%20-%20Exploits/README.md)

DeepSeek downloaded a public PoC for Langflow CVE-2026-33017. The report does not establish material modification.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0006 - Active Scanning](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md)

DeepSeek ran the public Langflow scanner and identified a target running Langflow 1.3.4.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

DeepSeek attempted exploitation, but no target exposed either required prerequisite. No access was obtained.

**Next**  [S12](#step-s12)

### Step S12

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md)

DeepSeek assessed Langflow as low value, surveyed exposure across 10 product families, compared vulnerability severity, deployment footprint, PoC availability, and prerequisites, and selected n8n.

**Next**  [S13](#step-s13)

### Step S13

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0095.000 - Code Repositories](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0095%20-%20Search%20Open%20Websites%20-%20Domains/AML.T0095.000%20-%20Code%20Repositories/README.md)

DeepSeek searched GitHub for trending 2026 CVE PoC repositories sorted by stars.

**Next**  [S14](#step-s14)

### Step S14

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.003 - Exploits](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.003%20-%20Exploits/README.md)

DeepSeek downloaded the public n8n PoC chaining CVE-2026-21858 and CVE-2025-68613 and inspected its affected versions and prerequisites.

**Next**  [S15](#step-s15)

### Step S15

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0000 - Search Open Technical Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)

DeepSeek queried FOFA for n8n deployments. FOFA reported 647,017 global results and 25,209 in China; these were not confirmed vulnerable systems.

**Next**  [S16](#step-s16)

### Step S16

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0006 - Active Scanning](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md)

DeepSeek sampled approximately 100 Chinese addresses, probed roughly 40 unique systems, identified three running affected versions, inspected form endpoints, and launched parallel scanning against more than 50 remaining targets.

**Next**  [S17](#step-s17)

### Step S17

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

DeepSeek attempted to find and exploit a system meeting the PoC prerequisites. All discovered forms required authentication, and no attempt produced file read, code execution, or initial access.

**Next**  End of path

## Attributed to

- [AML.E0038 - knaithe](../../Entities/AML.E0038%20-%20knaithe.md) (Adversarial Operation)

## Reported by

- [AML.E0034 - Unit 42](../../Entities/AML.E0034%20-%20Unit%2042.md)

## References

- [Chinese-Speaking Threat Actor Harnesses AI Models for Autonomous Cyberattacks](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0070)
