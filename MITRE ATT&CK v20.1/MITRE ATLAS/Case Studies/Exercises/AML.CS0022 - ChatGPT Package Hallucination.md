# AML.CS0022 - ChatGPT Package Hallucination

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers identified that large language models such as ChatGPT can hallucinate fake software package names that are not published to a package repository. An attacker could publish a malicious package under the hallucinated name to a package repository. Then users of the same or similar large language models may encounter the same hallucination and ultimately download and execute the malicious package leading to a variety of potential harms.

**Type**  Exercise

**Target**  ChatGPT users

**Activity period**  2024-06

## Procedure steps

### Step S00

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0040 - AI Model Inference API Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md)

The researchers use the public ChatGPT API throughout this exercise.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0062 - Discover LLM Hallucinations](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0062%20-%20Discover%20LLM%20Hallucinations/README.md)

The researchers prompt ChatGPT to suggest software packages and identify suggestions that are hallucinations which don't exist in a public package repository.

For example, when asking the model "how to upload a model to huggingface?" the response included guidance to install the `huggingface-cli` package with instructions to install it by `pip install huggingface-cli`. This package was a hallucination and does not exist on PyPI. The actual HuggingFace CLI tool is part of the `huggingface_hub` package.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0060 - Publish Hallucinated Entities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0060%20-%20Publish%20Hallucinated%20Entities/README.md)

An adversary could upload a malicious package under the hallucinated name to PyPI or other package registries.

In practice, the researchers uploaded an empty package to PyPI to track downloads.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.001 - Software](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.001%20-%20Software/README.md)

A user of ChatGPT or other LLM may ask similar questions which lead to the same hallucinated package name and cause them to download the malicious package.

The researchers showed that multiple LLMs can produce the same hallucinations. They tracked over 30,000 downloads of the `huggingface-cli` package.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.001 - Malicious Package](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.001%20-%20Malicious%20Package/README.md)

The user would ultimately load the malicious package, allowing for arbitrary code execution.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

This could lead to a variety of harms to the end user or organization.

**Next**  End of path

## Attributed to

- [AML.E0008 - Tenable](../../Entities/AML.E0008%20-%20Tenable.md) (Security Evaluation)
- [AML.E0009 - Lasso Security](../../Entities/AML.E0009%20-%20Lasso%20Security.md) (Security Evaluation)

## References

- [Vulcan18's "Can you trust ChatGPT's package recommendations?"](https://vulcan.io/blog/ai-hallucinations-package-risk)
- [Lasso Security Research: Diving into AI Package Hallucinations](https://www.lasso.security/blog/ai-package-hallucinations)
- [AIID Incident 731: Hallucinated Software Packages with Potential Malware Downloaded Thousands of Times by Developers](https://incidentdatabase.ai/cite/731/)
- [Slopsquatting: When AI Agents Hallucinate Malicious Packages](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/slopsquatting-when-ai-agents-hallucinate-malicious-packages)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0022)
