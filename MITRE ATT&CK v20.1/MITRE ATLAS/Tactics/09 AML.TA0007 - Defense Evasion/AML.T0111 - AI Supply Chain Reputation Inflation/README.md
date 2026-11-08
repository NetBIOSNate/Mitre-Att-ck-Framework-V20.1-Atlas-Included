# AML.T0111 - AI Supply Chain Reputation Inflation

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

AI Supply Chain Reputation Inflation is the process of building or leveraging genuinely credible-looking trust signals to increase the perceived legitimacy of AI supply chain components, with the goal of driving adoption of malicious or compromised assets.

Adversaries use established developer accounts with a history of legitimate projects and contributions to publish AI models, datasets, packages, and MCP servers that appear trustworthy. They build reputation through real adoption signals such as downloads, GitHub stars, forks, and inclusion in dependency chains, often releasing benign versions before introducing malicious updates via [AI Supply Chain Rug Pull](../AML.T0109%20-%20AI%20Supply%20Chain%20Rug%20Pull/README.md).

By relying on authentic history and usage patterns, these components pass both human and automated trust checks, increasing the likelihood they are adopted without scrutiny.

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0049 - Supply Chain Compromise via Poisoned ClawdBot Skill](../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md#step-s04)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0111)
