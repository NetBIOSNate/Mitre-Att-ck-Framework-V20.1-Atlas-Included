# AML.T0061 - LLM Prompt Self-Replication

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may introduce a prompt designed to replicate itself in a large language model's (LLM) output. The reproduced instructions may appear in generated messages, documents, source-code, files, or other artifacts. The prompt may direct the AI system to copy the instructions themselves or reproduce enclosing content that contains them. The self-replication instructions may be paired with additional malicious objectives, such as collecting sensitive information, modifying files, or invoking tools on the adversary's behalf.

Self-replicating prompts can persist in artifacts on the victim system. When retrieved and ingested by another LLM, the adversary's instructions are re-introduced, potentially long after the original interaction has ended. These retained copies may allow the adversary's influence to survive removal of the original malicious prompt payload without requiring the adversary to deliver it again.

Adversaries may deliver self-replicating prompts via [LLM Prompt Injection](../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md). Replicated instructions may support [LLM Prompt Propagation](../../12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md) when the generated content is passed to and ingested by other AI systems or components. The payload may also include instructions to bypass model safeguards through [LLM Jailbreak](../../08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0054%20-%20LLM%20Jailbreak/README.md) or pursue objectives such as [Exfiltration](../../15%20AML.TA0010%20-%20Exfiltration/README.md).

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s07)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect generated responses for reproduction of malicious instructions from input content. Block or quarantine instruction-bearing output when it reproduces an attack payload rather than fulfilling the authorized task.
- [AML.M0021 - Generative AI Guidelines](../../../Mitigations/AML.M0021%20-%20Generative%20AI%20Guidelines.md) — Guidelines can help instruct the model to produce more secure output, preventing the model from generating self-replicating outputs.
- [AML.M0022 - Generative AI Model Alignment](../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Model alignment can increase the security of models to self replicating prompt attacks.

## References

- [Self-replicating prompt injections exist](https://alignment.openai.com/misalignment-reports/self-replicating-prompt-injections-exist/)
- [Here Comes The AI Worm: Unleashing Zero-click Worms that Target GenAI-Powered Applications](https://arxiv.org/abs/2403.02817)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0061)
