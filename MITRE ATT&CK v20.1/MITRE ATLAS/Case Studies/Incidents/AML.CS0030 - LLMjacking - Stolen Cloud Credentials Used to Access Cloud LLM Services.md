# AML.CS0030 - LLMjacking: Stolen Cloud Credentials Used to Access Cloud LLM Services.

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

The Sysdig Threat Research Team discovered that malicious actors utilized stolen credentials to gain access to cloud-hosted large language models (LLMs). The actors covertly gathered information about which models were enabled on the cloud service and created a reverse proxy for LLMs that would allow them to provide model access to cybercriminals.

The Sysdig researchers identified tools used by the unknown actors that could target a broad range of cloud services including AI21 Labs, Anthropic, AWS Bedrock, Azure, ElevenLabs, MakerSuite, Mistral, OpenAI, OpenRouter, and GCP Vertex AI. Their technical analysis represented in the procedure below looked at at Amazon CloudTrail logs from the Amazon Bedrock service.

The Sysdig researchers estimated that the worst-case financial harm for the unauthorized use of a single Claude 2.x model could be up to $46,000 a day.

Update as of April 2025: This attack is ongoing and evolving. This case study only covers the initial reporting from Sysdig.

**Type**  Incident

**Actor**  Unknown

**Target**  Cloud-Based LLM Services

**Reporter**  Sysdig Threat Research

**Activity period**  2024-05-06

## Procedure steps

### Step S00

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

The adversaries exploited a vulnerable version of Laravel ([CVE-2021-3129](https://www.cve.org/CVERecord?id=CVE-2021-3129)) to gain initial access to the victims' systems.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

The adversaries found unsecured credentials to cloud environments on the victims' systems

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0139 - Compromise Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0139%20-%20Compromise%20Accounts/README.md)

The stolen cloud credentials supplied compromised accounts that the adversaries could use to obtain LLM-service capacity at the account holders' expense and support proxy-mediated access.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

The compromised credentials gave the adversaries access to cloud environments where large language model (LLM) services were hosted.

**Next**  [S05](#step-s05)

### Step S04

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.001 - Software Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.001%20-%20Software%20Tools/README.md)

The adversaries obtained [keychecker](https://github.com/cunnymessiah/keychecker), a bulk key checker for various AI services which is capable of testing if the key is valid and retrieving some attributes of the account (e.g. account balance and available models).

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0075 - Enterprise Resource Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0075%20-%20Enterprise%20Resource%20Discovery/README.md)

The adversaries used keychecker to discover which LLM services were enabled in the cloud environment and if the resources had any resource quotas for the services.

Then, the adversaries checked to see if their stolen credentials gave them access to the LLM resources. They used legitimate `invokeModel` queries with an invalid value of -1 for the `max_tokens_to_sample` parameter, which would raise an `AccessDenied` error if the credentials did not have the proper access to invoke the model. This test revealed that the stolen credentials did provide them with access to LLM resources.

The adversaries also used `GetModelInvocationLoggingConfiguration` to understand how the model was configured. This allowed them to see if prompt logging was enabled to help them avoid detection when executing prompts.

**Next**  [S07](#step-s07)

### Step S06

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.001 - Software Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.001%20-%20Software%20Tools/README.md)

The adversaries then used [OAI Reverse Proxy](https://gitgud.io/khanon/oai-reverse-proxy)  to create a reverse proxy service in front of the stolen LLM resources. The reverse proxy service could be used to sell access to cybercriminals who could exploit the LLMs for malicious purposes.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.005 - AI Service Proxies](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md)

The adversaries used reverse-proxy tooling with compromised cloud credentials to mediate access to LLM services. This infrastructure could support resale of access while usage was billed to the legitimate account holder.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.000 - Financial Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.000%20-%20Financial%20Harm/README.md)

In addition to providing cybercriminals with covert access to LLM resources, the unauthorized use of these LLM models could cost victims thousands of dollars per day.

**Next**  End of path

## Uses

- [AML.S0008 - keychecker](../../Software/Tools/AML.S0008%20-%20keychecker.md) — The adversaries used [keychecker](../../Software/Tools/AML.S0008%20-%20keychecker.md) to test stolen credentials for access to cloud-hosted AI services and identify available models and quotas. They also queried logging settings where supported to assess whether subsequent model use would be recorded. [ref-1](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)
- [AML.S0009 - OAI Reverse Proxy](../../Software/Tools/AML.S0009%20-%20OAI%20Reverse%20Proxy.md) — The adversaries attempted to access cloud-hosted models using stolen credentials with a user-agent matching [OAI Reverse Proxy](../../Software/Tools/AML.S0009%20-%20OAI%20Reverse%20Proxy.md). [ref-1](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)

## References

- [LLMjacking: Stolen Cloud Credentials Used in New AI Attack](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)
- [The Growing Dangers of LLMjacking: Evolving Tactics and Evading Sanctions](https://sysdig.com/blog/growing-dangers-of-llmjacking/)
- [LLMjacking targets DeepSeek](https://sysdig.com/blog/llmjacking-targets-deepseek/)
- [AIID Incident 898: Alleged LLMjacking Targets AI Cloud Services with Stolen Credentials](https://incidentdatabase.ai/cite/898)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0030)
