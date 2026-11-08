# AML.T0084.003 - Call Chains

[MITRE ATLAS](../../../../README.md) / [AML.TA0008 - Discovery](../../README.md) / [AML.T0084 - Discover AI Agent Configuration](../README.md)

Adversaries may extract call chains from AI agent configurations, which can reveal potentially targets for remote code execution (RCE) or other vulnerabilities. Vulnerable call chains often connect user inputs or LLM outputs to an execution sink (e.g. exec, eval, os.popen). The vulnerabilities may be later exploited via [LLM Prompt Injection](../../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md).

Adversaries may systematically identify potentially vulnerable call chains present in LLM frameworks, then scan for applications that are configured to use these call chains for targeting  [arxiv](https://arxiv.org/abs/2309.02926).

**Tactics**  [AML.TA0008 - Discovery](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0052 - LLMSmith: RCE Vulnerabilities in LLM-Integrated Applications](../../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md#step-s02)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Limit public disclosure of agent call chains and execution-sink details.

## References

- [\[2309.02926\] Demystifying RCE Vulnerabilities in LLM-Integrated Apps](https://arxiv.org/abs/2309.02926)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0084.003)
