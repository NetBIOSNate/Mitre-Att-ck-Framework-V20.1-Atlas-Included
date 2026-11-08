# AML.M0022 - Generative AI Model Alignment

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Generative AI Model Alignment is the process of training or fine-tuning a generative model to guide its output toward a set of human values, goals, or ethical principles. Desired principles can be in alignment with safety, security, content policies, and legal requirements, with goals such as removing harmful content or hallucinations, reducing biases, increasing predictability, and ensuring models do not have adverse societal consequences. In the context of agentic AI, alignment is about producing models that make decisions in support of the goals of the organization and individual users, with actions that remain in scope of the designated task, and designing agents that follow security standards, exhibit transparency in decision making, and operate within organizational boundaries.

Common methods for aligning a generative model during training or fine-tuning include [ibm-llm-alignment](https://www.ibm.com/think/topics/llm-alignment) [meta-llama](https://ai.meta.com/static-resource/responsible-use-guide/):
- Reinforcement Learning from Human or AI Feedback (RLHF or RLAIF)
- Supervised Fine-Tuning (SFT)
- Targeted Safety Context Distillation
- Instruction Tuning
- Direct Preference Optimization (DPO)
- Constitutional AI
- Incoulation Prompting

For agentic systems, alignment depends on the purpose of the agent, the tools available to the agent, and the levels of privileges and risks associated with tool calls. Standard alignment methods for LLMs can often be used in conjunction with domain-specific fine-tuning data, reward signals with examples of correct tool calls, or reinforcement learning based on interactions with a realistic environment. Examples of alignment methods specific to agentic AI are:
- Trajectory Preference Optimization [tpmm-dpo](https://arxiv.org/html/2605.23398v1)
- Environment-Driven Reinforcement Learning [envrl](https://arxiv.org/html/2606.17680v1)
- Reinforcement Learning with Execution Feedback (RLEF) [rlef](https://arxiv.org/abs/2410.02089)
- Reinforcement Learning with Verifiable Rewards (RLVR) [nvidia-mastering-agentic](https://developer.nvidia.com/blog/mastering-agentic-techniques-ai-agent-customization/)

Generative AI Model Alignment should be used in combination with [Generative AI Guardrails](AML.M0020%20-%20Generative%20AI%20Guardrails.md) and [Generative AI Guidelines](AML.M0021%20-%20Generative%20AI%20Guidelines.md). Models should be continually evaluated for alignment and retrained or fine-tuned systematically to incorporate observed failure modes or updated policies. It is important to also consider that fine-tuning a model can remove previously learned alignments and should be undertaken with care and a comprehensive plan for testing the updated model for safety and security.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  AI Model Engineering, AI Model Evaluation, Deployment

## Techniques mitigated

- [AML.T0016.002 - Generative AI](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.002%20-%20Generative%20AI/README.md) — Align generative models to resist and adversary's malicious requests and attempts to remove safety behavior.
- [AML.T0051 - LLM Prompt Injection](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md) — Model alignment can improve the parametric safety of a model by guiding it away from unsafe prompts and responses.
- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Model alignment can improve the parametric safety of a model by guiding it away from unsafe prompts and responses.
- [AML.T0054 - LLM Jailbreak](../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0054%20-%20LLM%20Jailbreak/README.md) — Model alignment can improve the parametric safety of a model by guiding it away from unsafe prompts and responses.
- [AML.T0061 - LLM Prompt Self-Replication](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0061%20-%20LLM%20Prompt%20Self-Replication/README.md) — Model alignment can increase the security of models to self replicating prompt attacks.
- [AML.T0062 - Discover LLM Hallucinations](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0062%20-%20Discover%20LLM%20Hallucinations/README.md) — Model alignment can help steer the model away from hallucinated content.
- [AML.T0085 - Data from AI Services](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/README.md) — Train or fine-tune models and agents to resist requests or injected instructions that induce collection or disclosure of sensitive information outside the authorized scope.
- [AML.T0085.000 - RAG Databases](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md) — Train or fine-tune models to resist requests and injected instructions that induce disclosure of sensitive retrieved information outside the authorized scope.
- [AML.T0085.001 - AI Agent Tools](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md) — Train or fine-tune agents to keep information-retrieval tool calls within the authorized task and resist requests or injected instructions that induce collection of unrelated or restricted information.
- [AML.T0085.002 - Conversation Context and Memory](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.002%20-%20Conversation%20Context%20and%20Memory/README.md) — Train or fine-tune models to resist requests to disclose sensitive conversation content or retained memory outside the authorized scope.
- [AML.T0085.003 - System Instructions](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.003%20-%20System%20Instructions/README.md) — Train or fine-tune models to resist requests to reproduce, summarize, or transform protected system instructions in ways that disclose their contents.
- [AML.T0102 - Generate Malicious Commands](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0102%20-%20Generate%20Malicious%20Commands/README.md) — Align generative AI models with safety objectives to reduce the likelihood that they will generate malicious commands or harmful instructions.
- [AML.T0145 - Poison AI Agent Learning Environment](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0145%20-%20Poison%20AI%20Agent%20Learning%20Environment/README.md) — Train or fine-tune models to follow intended policies and resist malicious instructions and unsafe tool use. Re-evaluate alignment after learning or adaptation to identify deviations caused by environment poisoning.

## References

- [What is LLM alignment?](https://www.ibm.com/think/topics/llm-alignment)
- [Meta Llama: Responsible Use Guide](https://ai.meta.com/static-resource/responsible-use-guide/)
- [TPMM-DPO: Trajectory-aware Preference-guided Model Merging for Iterative Direct Preference Optimization](https://arxiv.org/html/2605.23398v1)
- [EnvRL: Learn from Environment Dynamics in Agentic Reinforcement Learning](https://arxiv.org/html/2606.17680v1)
- [RLEF: Grounding Code LLMs in Execution Feedback with Reinforcement Learning](https://arxiv.org/abs/2410.02089)
- [Mastering Agentic Techniques: AI Agent Customization](https://developer.nvidia.com/blog/mastering-agentic-techniques-ai-agent-customization/)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0022)
