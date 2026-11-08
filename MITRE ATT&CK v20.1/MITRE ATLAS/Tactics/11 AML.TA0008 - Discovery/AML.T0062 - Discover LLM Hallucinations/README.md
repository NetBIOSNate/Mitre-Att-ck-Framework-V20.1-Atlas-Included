# AML.T0062 - Discover LLM Hallucinations

[MITRE ATLAS](../../../README.md) / [AML.TA0008 - Discovery](../README.md)

Adversaries may prompt large language models and identify hallucinated entities.
They may request software packages, commands, URLs, organization names, or e-mail addresses, and identify hallucinations with no connected real-world source. Discovered hallucinations provide the adversary with potential targets to [Publish Hallucinated Entities](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0060%20-%20Publish%20Hallucinated%20Entities/README.md). Different LLMs have been shown to produce the same hallucinations, so the hallucinations exploited by an adversary may affect users of other LLMs.

**Tactics**  [AML.TA0008 - Discovery](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0022 - ChatGPT Package Hallucination](../../../Case%20Studies/Exercises/AML.CS0022%20-%20ChatGPT%20Package%20Hallucination.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0022%20-%20ChatGPT%20Package%20Hallucination.md#step-s01)

## Mitigations

- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit repeated prompts used to search for exploitable hallucinations.
- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Check generated package names, commands, URLs, and other externally verifiable entities against authoritative sources before presenting them as valid. Suppress or flag unsupported entities to reduce opportunities for adversaries to identify exploitable hallucinations through the protected service.
- [AML.M0021 - Generative AI Guidelines](../../../Mitigations/AML.M0021%20-%20Generative%20AI%20Guidelines.md) — Guidelines can instruct the model to avoid producing hallucinated content.
- [AML.M0022 - Generative AI Model Alignment](../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Model alignment can help steer the model away from hallucinated content.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0062)
