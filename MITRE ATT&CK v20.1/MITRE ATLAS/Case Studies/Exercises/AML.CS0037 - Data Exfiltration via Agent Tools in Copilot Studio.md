# AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers from Zenity demonstrated how an organization's data can be exfiltrated via prompt injections that target an AI-powered customer service agent.

The target system is a customer service agent built by Zenity in Copilot Studio. It is modeled after an agent built by McKinsey to streamline its customer service needs. The AI agent listens to a customer service email inbox where customers send their engagement requests. Upon receiving a request, the agent looks at the customer's previous engagements, understands who the best consultant for the case is, and proceeds to send an email to the respective consultant regarding the request, including all of the relevant context the consultant will need to properly engage with the customer.

The Zenity researchers begin by performing targeting to identify an email inbox that is managed by an AI agent. Then they use prompt injections to discover details about the AI agent, such as its knowledge sources and tools. Once they understand the AI agent's capabilities, the researchers are able to craft a prompt that retrieves private customer data from the organization's RAG database and CRM, and exfiltrate it via the AI agent's email tool.

Vendor Response: Microsoft quickly acknowledged and fixed the issue. The prompts used by the Zenity researchers in this exercise no longer work, however other prompts may still be effective.

**Type**  Exercise

**Target**  Copilot Studio Customer Service Agent

**Activity period**  2025-06

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0006.003 - Probe AI Agent Trigger Channels](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/AML.T0006.003%20-%20Probe%20AI%20Agent%20Trigger%20Channels/README.md)

The researchers look for support email addresses on the target organization's website which may be managed by an AI agent. Then, they probe the system by sending emails and looking for indications of agentic AI in automatic replies.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

Once a target has been identified, the researchers craft prompts designed to probe for a potential AI agent monitoring the inbox. The prompt instructs the agent to send an email reply to an address of the researchers' choosing.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researchers send an email with the malicious prompt to the inbox they suspect may be managed by an AI agent.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.002 - Triggered](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.002%20-%20Triggered/README.md)

The researchers receive a reply at the address they specified, indicating that there is an AI agent present, and that the triggered prompt injection was successful.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0084.002 - Activation Triggers](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.002%20-%20Activation%20Triggers/README.md)

The researchers infer that the AI agent is activated when receiving an email.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0084.001 - Tool Definitions](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.001%20-%20Tool%20Definitions/README.md)

The researchers infer that the AI agent has a tool for sending emails.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0047 - AI-Enabled Product or Service](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md)

From here, the researchers repeat the same steps to interact with the AI agent, sending malicious prompts to the agent via email and receiving responses at their desired address.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051 - LLM Prompt Injection](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md)

The researchers modify the original prompt to discover other knowledge sources and tools that may have data they are after.

**Next**  [S08](#step-s08), [S09](#step-s09)

### Step S08

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0084.000 - Embedded Knowledge](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.000%20-%20Embedded%20Knowledge/README.md)

The researchers discover the AI agent has access to a "Customer Support Account Owners.csv" data source.

**Next**  [S10](#step-s10)

### Step S09

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0084.001 - Tool Definitions](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.001%20-%20Tool%20Definitions/README.md)

The researchers discover the AI agent has access to the Salesforce get-records tool, which can be used to retrieve CRM records.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers put their knowledge of the AI agent's tools and knowledge sources together to craft a prompt that will collect and exfiltrate the customer data they are after.

**Next**  [S11](#step-s11), [S12](#step-s12)

### Step S11

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.000 - RAG Databases](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md)

The prompt asks the agent to retrieve all of the fields and rows from "Customer Support Account Owners.csv". The agent retrieves the entire file.

**Next**  [S13](#step-s13)

### Step S12

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.001 - AI Agent Tools](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md)

The prompt asks the agent to retrieve all Salesforce records using its get-records tool. The agent retrieves all records from the victim's CRM.

**Next**  [S13](#step-s13)

### Step S13

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

The prompt asks the agent to email the results to an address of the researcher's choosing using its email tool. The researchers successfully exfiltrate their target data via the tool invocation.

**Next**  End of path

## Attributed to

- [AML.E0010 - Zenity](../../Entities/AML.E0010%20-%20Zenity.md) (Security Evaluation)

## References

- [AgentFlayer: Discovery Phase of AI Agents in Copilot Studio](https://labs.zenity.io/p/a-copilot-studio-story-discovery-phase-in-ai-agents-f917)
- [AgentFlayer: When AIjacking Leads to Full Data Exfiltration in Copilot Studio](https://labs.zenity.io/p/a-copilot-studio-story-2-when-aijacking-leads-to-full-data-exfiltration-bc4a)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0037)
