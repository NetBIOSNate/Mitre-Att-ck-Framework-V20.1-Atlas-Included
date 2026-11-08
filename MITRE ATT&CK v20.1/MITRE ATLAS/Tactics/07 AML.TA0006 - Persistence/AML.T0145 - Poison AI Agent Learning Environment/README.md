# AML.T0145 - Poison AI Agent Learning Environment

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may manipulate an environment in which an AI agent interacts so that observations, feedback, rewards, actions, or resulting interactions are incorporated into model training to cause persistent changes to the behavior of an AI system. This allows adversary's influence to persist beyond the original interaction and affect subsequent tasks.

An adversary may alter webpages, tool or API responses, elements in simulated environments, task descriptions, reward signals, evaluator outputs, or other environmental content used during AI agent learning or adaptation. The manipulated interactions may be incorporated into model fine-tuning, reinforcement learning, synthetic training corpora, agent memories, other  persistent components.

[Poison AI Agent Learning Environment](README.md) targets the process that generates or selects learning experience, without requiring direct adversarial access to training datasets, model parameters, or stored agent artifacts. The resulting experience may appear legitimate because it was produced by an authorized agent operating through an expected interface. Once introduced, the adversary's influence may remain effective even after the manipulated environmental content is removed or is no longer encountered.

An adversary may use this technique to introduce backdoors, increase compliance with malicious instructions, distort policies or preferences, teach unsafe tool use, manipulate reward-seeking behavior. The malicious behavior may be activated later by an environmental trigger or during ordinary agent operation.

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0007 - Sanitize Training Data](../../../Mitigations/AML.M0007%20-%20Sanitize%20Training%20Data.md) — Screen environmental content and resulting interaction data for poisoning before use in learning or adaptation. Quarantine and remediate affected data before use.
- [AML.M0008 - Validate AI Model](../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models after learning or adaptation using clean evaluation data and targeted tests for backdoors, unsafe tool use, and unexpected behavior. Compare results against trusted baselines and investigate unexplained deviations before deployment.
- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Independently check generated outputs and proposed actions against applicable policies at runtime. Block prohibited outputs and actions to limit the impact of learning from a poisoned environment.
- [AML.M0022 - Generative AI Model Alignment](../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Train or fine-tune models to follow intended policies and resist malicious instructions and unsafe tool use. Re-evaluate alignment after learning or adaptation to identify deviations caused by environment poisoning.
- [AML.M0025 - Maintain AI Dataset Provenance](../../../Mitigations/AML.M0025%20-%20Maintain%20AI%20Dataset%20Provenance.md) — Record the sources of environmental content and resulting interaction data used in learning or adaptation to trace suspicious learning experiences to their sources.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Introduce controlled manipulations into the agent's learning environment to test for persistent behavior changes. Verify poisoning detection and rejection controls, and remediate identified weaknesses.

## References

- [Malice in Agentland: Down the Rabbit Hole of Backdoors in the AI Supply Chain](https://arxiv.org/pdf/2510.05159)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0145)
