# AML.CS0069 - GTG-1002 Claude Code Espionage Campaign

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

In September 2025, GTG-1002 used a jailbroken Claude Code agent to conduct a cyber-espionage campaign against approximately 30 organizations, succeeding against a small number. Anthropic assessed with high confidence that GTG-1002 was a Chinese state-sponsored group.

GTG-1002 selected organizations in the technology, financial, chemical-manufacturing, and government sectors and configured an autonomous attack framework to operate against them. The operators obtained access to Claude Code and circumvented its safeguards by concealing their malicious purpose behind a false defensive-security persona and apparently benign tasks. GTG-1002 then connected the jailbroken Claude agent to scanners, browser automation, password crackers, database tooling, and dedicated penetration-testing servers through MCP.

Between operator-controlled stage gates, the adversary's jailbroken Claude agent autonomously inspected target infrastructure, identified high-value systems, scanned for vulnerabilities, and developed and deployed a tailored exploit chain for an identified SSRF vulnerability. After obtaining access to a target, it mapped internal resources and network relationships, found authentication certificates in system configuration files, used harvested credentials to access additional services, established a backdoor account, and collected sensitive information from local systems and internal databases.

The adversary's jailbroken Claude agent performed an estimated 80-90% of campaign activity, including processing collected data, categorizing it by intelligence value, and documenting attack progress. Human operators retained approximately four to six critical decisions per target, including review and approval before selected data was exfiltrated over the Claude web service.

**Type**  Incident

**Target**  30 entities in the technology, financial, chemical, and government sectors

**Activity period**  2025-09

## Procedure steps

### Step S01

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0040 - AI Model Inference API Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md)

GTG-1002 obtained access to Claude Code for use in its intrusion framework.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.000 - Direct](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.000%20-%20Direct/README.md)

GTG-1002 supplied Claude Code false authorization claims, a defensive-security persona, and apparently benign tasks.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0054 - LLM Jailbreak](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0054%20-%20LLM%20Jailbreak/README.md)

The deceptive prompts circumvented the Claude Code's safeguards, inducing it to perform offensive actions it was intended to refuse.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.001 - Software Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.001%20-%20Software%20Tools/README.md)

GTG-1002 obtained network scanners, database exploitation frameworks, password crackers, binary-analysis utilities, and other tools made available to the jailbroken Claude agent.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0128 - Compromise Infrastructure](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0128%20-%20Compromise%20Infrastructure/README.md)

GTG-1002 operated dedicated penetration-testing servers accessible through MCP to support remote command execution, simultaneous tool coordination, and persistent operational state across campaign sessions.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0103 - Deploy AI Agent](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0103%20-%20Deploy%20AI%20Agent/README.md)

GTG-1002 configured their Claude agent within an attack framework connected to scanners, browser automation, password crackers, database tooling, and dedicated penetration-testing servers.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md)

GTG-1002 assigned their Claude agent target-scoped objectives against a human-selected organization under false defensive-testing context. Between operator-controlled stage gates, the agent derived and revised intermediate actions for reconnaissance, vulnerability exploitation, credential access, internal navigation, collection, and exfiltration, selecting and invoking available tools based on operational results.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md)

GTG-1002's jailbroken Claude agent inspected the target's systems and infrastructure, used returned information to direct further investigation, and identified high-value databases and workflow orchestration platforms. Anthropic does not identify the victim, products, or databases involved.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0006 - Active Scanning](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md)

GTG-1002's jailbroken Claude agent performed IP-block scanning across ranges associated with the target organization and vulnerability scanning against its infrastructure. It used the scans to enumerate public-facing services and endpoints, identify potential vulnerabilities, and select an SSRF vulnerability in an unnamed public-facing application for further investigation. Reporting does not establish whether the vulnerability was previously known or assigned a CVE.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.001 - Autonomous Exploit Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.001%20-%20Autonomous%20Exploit%20Development/README.md)

GTG-1002's Claude agent researched exploitation techniques for the identified SSRF vulnerability, generated a tailored custom payload and full exploit chain, tested the approach, evaluated the results, and adapted it for the target.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

GTG-1002's jailbroken Claude agent deployed the tailored SSRF exploit against the public-facing application and obtained access to the target environment.

**Next**  [S12](#step-s12)

### Step S12

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0075 - Enterprise Resource Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0075%20-%20Enterprise%20Resource%20Discovery/README.md)

GTG-1002's jailbroken Claude agent cataloged services and data on discovered endpoints, searched for sensitive files and data, and used MCP-connected browser automation to enumerate internal databases, container registries, administrative interfaces, workflow orchestration platforms, and other network services. It also queried internal database user-account tables to enumerate accounts and identify high-privilege accounts.

**Next**  [S13](#step-s13)

### Step S13

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0089 - Enterprise Environment Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0089%20-%20Enterprise%20Environment%20Discovery/README.md)

GTG-1002's jailbroken Claude agent identified system and network configurations on discovered devices, including database types, and mapped the target's complete network topology, internal network architecture, and access relationships among systems and services.

**Next**  [S14](#step-s14)

### Step S14

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

GTG-1002's jailbroken Claude agent searched discovered system configuration files and extracted authentication certificates and other credential material. Reporting does not disclose the exact file paths, commands, hosts, or tools used.

**Next**  [S15](#step-s15)

### Step S15

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0012%20-%20Valid%20Accounts/README.md)

GTG-1002's jailbroken Claude agent tested harvested credentials against discovered devices and used valid credentials to authenticate to internal APIs, databases, container registries, and logging infrastructure.

**Next**  [S16](#step-s16)

### Step S16

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0125 - Create Account](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0125%20-%20Create%20Account/README.md)

GTG-1002's jailbroken Claude agent created a local backdoor account to maintain access to a compromised environment.

**Next**  [S17](#step-s17)

### Step S17

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0036 - Data from Information Repositories](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0036%20-%20Data%20from%20Information%20Repositories/README.md)

Using the authenticated access provided by the harvested credentials, GTG-1002's jailbroken Claude agent queried internal databases and systems for proprietary information, system configurations, and sensitive operational data.

**Next**  [S18](#step-s18)

### Step S18

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0037 - Data from Local System](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0037%20-%20Data%20from%20Local%20System/README.md)

Access obtained through the initial compromise also allowed GTG-1002's jailbroken Claude agent to gather credentials, system configurations, and sensitive operational data stored on compromised systems.

**Next**  [S19](#step-s19)

### Step S19

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0126 - Automated Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0126%20-%20Automated%20Collection/README.md)

GTG-1002's jailbroken Claude agent automatically collected and processed large volumes of victim data and categorized the results according to their intelligence value. It generated comprehensive documentation covering discovered services, harvested credentials, sensitive data, exploitation techniques, and attack progression to support subsequent campaign activity.

**Next**  [S20](#step-s20)

### Step S20

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0127 - Data Staged](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0127%20-%20Data%20Staged/README.md)

GTG-1002's jailbroken Claude agent categorized collected data by intelligence value, staged extracted data and operational documentation in structured Markdown files, and prepared a detailed summary for operator review.

**Next**  [S21](#step-s21)

### Step S21

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0136 - Exfiltration via AI User Interface](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0136%20-%20Exfiltration%20via%20AI%20User%20Interface/README.md)

After reviewing the summary, GTG-1002 approved the transfer of selected data over the Claude web service.

**Next**  End of path

## Attributed to

- [AML.E0037 - GTG-1002](../../Entities/AML.E0037%20-%20GTG-1002.md) (Adversarial Operation)

## Reported by

- [AML.E0039 - Anthropic](../../Entities/AML.E0039%20-%20Anthropic.md)

## References

- [Disrupting the First Reported AI-Orchestrated Cyber Espionage Campaign](https://www.anthropic.com/news/disrupting-AI-espionage)
- [Anthropic AI-Orchestrated Campaign C0062](https://attack.mitre.org/campaigns/C0062/)
- [AIID - Incident 1263: Chinese State-Linked Operator (GTG-1002) Reportedly Uses Claude Code for Autonomous Cyber Espionage](https://incidentdatabase.ai/cite/1263/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0069)
