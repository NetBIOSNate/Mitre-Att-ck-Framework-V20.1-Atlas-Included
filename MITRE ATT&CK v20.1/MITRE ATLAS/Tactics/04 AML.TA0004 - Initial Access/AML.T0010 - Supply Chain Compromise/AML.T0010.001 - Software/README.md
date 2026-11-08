# AML.T0010.001 - Software

[MITRE ATLAS](../../../../README.md) / [AML.TA0004 - Initial Access](../../README.md) / [AML.T0010 - Supply Chain Compromise](../README.md)

Adversaries may target software packages that are commonly used in AI-enabled systems or are part of the AI DevOps lifecycle. This can include deep learning frameworks used to build AI models (e.g. PyTorch, TensorFlow, Jax), generative AI integration frameworks (e.g. LangChain, LangFlow), inference engines, and AI DevOps tools. They may also target the dependency chains of any of these software packages  [pytorch](https://pytorch.org/blog/compromised-nightly-dependency/). Additionally, adversaries may target specific components used by AI software such as configuration files  [pillar](https://www.pillar.security/blog/new-vulnerability-in-github-copilot-and-cursor-how-hackers-can-weaponize-code-agents) or example usage of AI packages, which may be distributed in Jupyter notebooks  [medium](https://medium.com/mlearning-ai/careful-who-you-colab-with-fa8001f933e7).

Adversaries may compromise legitimate packages  [aws](https://aws.amazon.com/security/security-bulletins/AWS-2025-015/) or publish malicious software to a namesquatted location  [pytorch](https://pytorch.org/blog/compromised-nightly-dependency/). They may target package names that are hallucinated by large language models  [trendmicro](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/slopsquatting-when-ai-agents-hallucinate-malicious-packages) (see: Publish Hallucinated Entities). They may also perform an [AI Supply Chain Rug Pull](../../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0109%20-%20AI%20Supply%20Chain%20Rug%20Pull/README.md) in which they first publish a legitimate package and then publish a malicious version once they reach a critical mass of users.

**Tactics**  [AML.TA0004 - Initial Access](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1195.002](../../../../../Enterprise/Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.002%20-%20Compromise%20Software%20Supply%20Chain/README.md) · [MITRE ATT&CK T1195.002](https://attack.mitre.org/techniques/T1195/002/)

## Case studies

- [AML.CS0015 - Compromised PyTorch Dependency Chain](../../../../Case%20Studies/Incidents/AML.CS0015%20-%20Compromised%20PyTorch%20Dependency%20Chain.md) · [S00](../../../../Case%20Studies/Incidents/AML.CS0015%20-%20Compromised%20PyTorch%20Dependency%20Chain.md#step-s00)
- [AML.CS0018 - Arbitrary Code Execution with Google Colab](../../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md) · [S01](../../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md#step-s01)
- [AML.CS0022 - ChatGPT Package Hallucination](../../../../Case%20Studies/Exercises/AML.CS0022%20-%20ChatGPT%20Package%20Hallucination.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0022%20-%20ChatGPT%20Package%20Hallucination.md#step-s03)
- [AML.CS0041 - Rules File Backdoor: Supply Chain Attack on AI Coding Assistants](../../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md#step-s03)
- [AML.CS0047 - Code to Deploy Destructive AI Agent Discovered in Amazon Q VS Code Extension](../../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md) · [S02](../../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md#step-s02)
- [AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations](../../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md) · [S14](../../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s14)

## Mitigations

- [AML.M0013 - Code Signing](../../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Enforce properly signed drivers and ML software frameworks.
- [AML.M0014 - Verify AI Artifacts](../../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify software packages and supporting artifacts, including configuration files and notebooks, against approved digests or signed manifests before installation or use. Reject unauthorized substitutions or changes.
- [AML.M0023 - Maintain an AI Bill of Materials](../../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Record AI software packages, frameworks, inference engines, and DevOps tools, including versions and dependencies. Use these records to identify deployments affected by reported software compromises and guide replacement or rollback.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Introduce controlled untrusted AI packages, libraries, plugins, or software components. Verify dependency controls, scanning, signing, approval, isolation, and safe installation.
- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on compromised software packages, dependencies, and releases, including affected versions and distribution locations. Use this intelligence to identify affected software, prevent its introduction into downstream systems, and prioritize investigation and replacement.

## Software implementations

- [AML.S0004 - torchtriton](../../../../Software/Malware/AML.S0004%20-%20torchtriton.md) — The malicious [torchtriton](../../../../Software/Malware/AML.S0004%20-%20torchtriton.md) package impersonated a PyTorch-nightly dependency on PyPI. Package resolution selected it instead of the legitimate dependency hosted on PyTorch's nightly index, introducing its payload into affected Linux Python environments. [source-1](https://pytorch.org/blog/compromised-nightly-dependency/)

## References

- [Security Update for Amazon Q Developer Extension for Visual Studio Code (Version #1.84)](https://aws.amazon.com/security/security-bulletins/AWS-2025-015/)
- [Careful Who You Colab With: abusing google colaboratory](https://medium.com/mlearning-ai/careful-who-you-colab-with-fa8001f933e7)
- [New Vulnerability in GitHub Copilot and Cursor: How Hackers Can Weaponize Code Agents](https://www.pillar.security/blog/new-vulnerability-in-github-copilot-and-cursor-how-hackers-can-weaponize-code-agents)
- [Compromised PyTorch-nightly dependency chain between December 25th and December 30th, 2022.](https://pytorch.org/blog/compromised-nightly-dependency/)
- [Slopsquatting: When AI Agents Hallucinate Malicious Packages](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/slopsquatting-when-ai-agents-hallucinate-malicious-packages)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0010.001)
