# AML.T0080.001 - Thread

[MITRE ATLAS](../../../../README.md) / [AML.TA0006 - Persistence](../../README.md) / [AML.T0080 - AI Agent Context Poisoning](../README.md)

Adversaries may introduce malicious instructions into a chat thread of a large language model (LLM) to cause behavior changes which persist for the remainder of the thread. A chat thread may continue for an extended period over multiple sessions.

The malicious instructions may be introduced via Direct or Indirect Prompt Injection. Direct Injection may occur in cases where the adversary has acquired a user's LLM API keys and can inject queries directly into any thread.

As the token limits for LLMs rise, AI systems can make use of larger context windows which allow malicious instructions to persist longer in a thread.
Thread Poisoning may affect multiple users if the LLM is being used in a service with shared threads. For example, if an agent is active in a Slack channel with multiple participants, a single malicious message from one user can influence the agent's behavior in future interactions with others.

**Tactics**  [AML.TA0006 - Persistence](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0036 - AIKatz: Attacking LLM Desktop Applications](../../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s06)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S15](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s15)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s05)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Evaluate retained conversation content and summaries for malicious instructions that could influence later turns. Recheck proposed actions against authorized objectives throughout the thread rather than treating previously accepted content as trusted.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Introduce controlled malicious instructions into long-lived or shared conversation threads. Verify context isolation, trust handling, thread reset, expiration, and monitoring.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0080.001)
