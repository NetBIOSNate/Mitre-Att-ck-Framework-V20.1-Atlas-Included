# AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

In early July 2026, an unknown Chinese-language operator used a multi-agent framework built on Hermes and OpenClaw against government systems that subsequent public reporting identified as Taiwanese. [financial-times-taiwan-ai-attack](https://www.ft.com/content/7d2ab3e0-9085-48f6-b38a-d90260d58795) Dream Research Labs recovered a 160 MB operational workspace containing 1,395 files documenting 12 attack waves conducted from July 1 through July 4. [dream-multi-agent-framework](https://www.dreamgroup.com/blog/inside-a-multi-agent-ai-framework-used-to-compromise-government-entities-in-asia) Taiwan's Ministry of Digital Affairs separately confirmed [moda-ai-agent-attacks](https://moda.gov.tw/ACS/press/news/press/20394) detecting abnormal attacks during July involving a hybrid of human operation and OpenClaw-assisted activity.

The agentic AI framework coordinated up to eight specialized sub-agents concurrently across reconnaissance, authentication attacks, API testing, vulnerability research, and exploitation. A probabilistic decision engine ranked findings and 14 candidate attack paths, allocated additional testing to promising results, discarded invalidated paths, and used after-action reports to redirect subsequent activity.

Starting from an internet-facing government portal, the framework decompiled client-side application bundles and mapped connected systems, identity infrastructure, and exposed APIs. It obtained access through exposed debug endpoints, unsigned JWT acceptance, and password spraying based on personnel identifiers collected from unauthenticated APIs. Tesseract OCR automated CAPTCHA solving, reportedly helping compromise 85 accounts, 84 of which authenticated to another government system through an SSO bridge without additional MFA or user confirmation.

Dream Research Labs reported the extraction of more than 2,564 personnel records, a complete user-database export, SSO configuration and client information, database credentials, and internal network ranges.

**Type**  Incident

**Actor**  Unknown Chinese-language actor

**Target**  Taiwanese government agencies and connected government systems

**Reporter**  Dream Research Labs

**Activity period**  2026-07-01 to 2026-07-04

## Procedure steps

### Step S01

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0124 - Autonomous Attack Orchestration](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md)

The framework dispatched up to eight specialized agents concurrently across 12 attack waves. It assigned separate reconnaissance, authentication, API-testing, vulnerability-research, credential, and exploitation missions; allocated additional testing to promising findings; requested independent validation; aggregated after-action reports; and redirected subsequent work based on the status of related workstreams.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md)

The framework constructed numerous candidate multi-step attack paths using confirmed prerequisites, observed blockers, and estimated success probabilities. It promoted paths supported by validated evidence, queued paths requiring additional investigation, discarded false positives and blocked paths, and initiated target-specific learning cycles when existing methods failed.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0118.001 - Direct Agent Communication](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md)

The framework exchanged assignments, findings, validation results, status, and after-action information between its orchestrating control process and specialized sub-agents. Aggregated results informed later assignments and attack waves.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md)

The framework performed reconnaissance on an internet-facing Taiwanese government portal, interpreting client-side application bundles, following discovered infrastructure relationships, and generating additional reconnaissance objectives. It identified 21 connected systems, six SSO sub-realms, authentication configuration, signing-key information, and more than 36 API endpoints on one system.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0006 - Active Scanning](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md)

The framework probed primary government applications and APIs for exposed interfaces, authentication behavior, misconfigurations, and vulnerabilities. This scanning identified multiple potential paths into the targeted systems.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0036 - Data from Information Repositories](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0036%20-%20Data%20from%20Information%20Repositories/README.md)

The framework retrieved employee names, departments, identifiers, and SSO account information from an exposed user-database API without authentication.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

The framework used employee identifiers obtained from the exposed API to test predictable password patterns against the office automation portal. The framework successfully authenticated to the office automation portal using the compromised employee accounts.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0012%20-%20Valid%20Accounts/README.md)

The framework systematically tested the 85 compromised office automation accounts against another government information system through an SSO bridge that trusted the existing office automation sessions, providing access to internal dashboards, equipment management interfaces, and personnel statistics pages.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

The framework abused three exposed debug endpoints that accepted arbitrary request bodies and returned authenticated sessions.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

The framework found a public-facing API that accepted unsigned JWTs with `alg=none`, allowing identity tokens to be forged without the signing key.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0126 - Automated Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0126%20-%20Automated%20Collection/README.md)

Using the acquired accesses, the framework automatically retrieved and aggregated the reported personnel, account, configuration, credential, and network information.

**Next**  [S12](#step-s12)

### Step S12

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

Over 2,564 personnel records, a complete user database, and internal architecture details were exfiltrated.

**Next**  End of path

## Uses

- [AML.S0025 - Hermes Agent](../../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) — The operator used a multi-agent framework built on [Hermes Agent](../../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) and [OpenClaw](../../Software/Tools/AML.S0026%20-%20OpenClaw.md) to coordinate parallel reconnaissance, credential attacks, API testing, and data collection against government systems. [dream-multi-agent-framework](https://www.dreamgroup.com/blog/inside-a-multi-agent-ai-framework-used-to-compromise-government-entities-in-asia)
- [AML.S0026 - OpenClaw](../../Software/Tools/AML.S0026%20-%20OpenClaw.md) — The operator used a multi-agent framework built on [Hermes Agent](../../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) and [OpenClaw](../../Software/Tools/AML.S0026%20-%20OpenClaw.md) to coordinate parallel reconnaissance, credential attacks, API testing, and data collection against government systems. [dream-multi-agent-framework](https://www.dreamgroup.com/blog/inside-a-multi-agent-ai-framework-used-to-compromise-government-entities-in-asia)
- [AML.S0027 - Tesseract OCR](../../Software/Tools/AML.S0027%20-%20Tesseract%20OCR.md) — The operator's multi-agent framework used [Tesseract OCR](../../Software/Tools/AML.S0027%20-%20Tesseract%20OCR.md) to solve image-based CAPTCHA challenges during automated password-spraying attempts against a government portal. [dream-multi-agent-framework](https://www.dreamgroup.com/blog/inside-a-multi-agent-ai-framework-used-to-compromise-government-entities-in-asia)

## References

- [Inside a Multi-Agent AI Framework Used to Compromise Government Entities in Asia](https://www.dreamgroup.com/blog/inside-a-multi-agent-ai-framework-used-to-compromise-government-entities-in-asia)
- [Overseas hackers launch AI-agent attacks against government agencies; MODA activates coordinated response and strengthens cyber defenses](https://moda.gov.tw/ACS/press/news/press/20394)
- [China-linked hackers hit Taiwan in unprecedented 'autonomous' AI cyber attack](https://www.ft.com/content/7d2ab3e0-9085-48f6-b38a-d90260d58795)
- [AIID - Incident 1646: Suspected China-Linked Hackers Reportedly Used AI Agents to Compromise Taiwanese Government Systems and Exfiltrate Personnel Records](https://incidentdatabase.ai/cite/1646/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0071)
