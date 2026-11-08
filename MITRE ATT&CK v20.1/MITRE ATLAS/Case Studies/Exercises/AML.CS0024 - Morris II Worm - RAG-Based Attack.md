# AML.CS0024 - Morris II Worm: RAG-Based Attack

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers developed Morris II, a zero-click worm designed to attack generative AI (GenAI) ecosystems and propagate between connected GenAI systems. The worm uses an adversarial self-replicating prompt which uses prompt injection to replicate the prompt as output and perform malicious activity.

The researchers demonstrate how this worm can propagate through an email system with a RAG-based assistant. They use a target system that automatically ingests received emails, retrieves past correspondences, and generates a reply for the user. To carry out the attack, they send a malicious email containing the adversarial self-replicating prompt, which ends up in the RAG database. The malicious instructions in the prompt tell the assistant to include sensitive user data in the response. Future requests to the email assistant may retrieve the malicious email. This leads to propagation of the worm due to the self-replicating portion of the prompt, as well as leaking private information due to the malicious instructions.

**Type**  Exercise

**Actor**  Stav Cohen, Ron Bitton, Ben Nassi

**Target**  RAG-based e-mail assistant

**Activity period**  2024-03-05

## Procedure steps

### Step S00

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0040 - AI Model Inference API Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md)

The researchers use access to the publicly available GenAI model API that powers the target RAG-based email system.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers construct an adversarial prompt containing instructions to reproduce itself in the model's output and include sensitive information extracted from the supplied context.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0042 - Verify Attack](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md)

The researchers evaluate the crafted prompts against public GenAI model APIs, checking whether the generated responses reproduce the malicious instructions and include sensitive information from the supplied context.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researchers send an email containing the adversarial self-replicating prompt to an address handled by the target RAG-based email assistant, introducing the malicious instructions into the victim's email environment.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0070 - RAG Poisoning](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0070%20-%20RAG%20Poisoning/README.md)

The email application stores the correspondence containing the malicious prompt in its RAG database as part of its normal processing. This contaminates the retrieval corpus, making the instructions available for inclusion in future reply-generation requests.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.002 - Triggered](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.002%20-%20Triggered/README.md)

A subsequent email from another client triggers automatic reply generation. The assistant retrieves the previously stored malicious correspondence as relevant context and includes it in the model request, causing the embedded instructions to influence the response.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0054 - LLM Jailbreak](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0054%20-%20LLM%20Jailbreak/README.md)

The malicious prompt uses role-play instructions to tell the model to become "Wormy," an email assistant that reproduces the injected instructions and discloses contact information from retrieved correspondence.

**Next**  [S07](#step-s07), [S08](#step-s08)

### Step S07

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0061 - LLM Prompt Self-Replication](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0061%20-%20LLM%20Prompt%20Self-Replication/README.md)

The self-replicating portion of the prompt causes the generated output to contain the malicious prompt, allowing the worm to propagate.

**Next**  [S10](#step-s10)

### Step S08

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.000 - RAG Databases](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md)

The injected instructions cause the model to extract sensitive information, such as email addresses, physical addresses, and phone numbers, from the correspondence retrieved into the request context and include it in the generated response.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

The email application sends the generated response, containing sensitive information extracted from retrieved correspondence, through its normal automatic email-reply workflow.

**Next**  [S11](#step-s11)

### Step S10

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0143 - LLM Prompt Propagation](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md)

The application sends the generated reply containing the reproduced malicious prompt to the client whose email triggered the response, allowing the prompt to propagate to other systems.

**Next**  End of path

### Step S11

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

Users of the GenAI email assistant may have PII leaked to attackers.

**Next**  End of path

## References

- [Here Comes The AI Worm: Unleashing Zero-click Worms that Target GenAI-Powered Applications](https://arxiv.org/abs/2403.02817)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0024)
