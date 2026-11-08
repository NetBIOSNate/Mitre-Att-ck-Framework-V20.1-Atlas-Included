# AML.S0007 - huggingface-cli

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[huggingface-cli](AML.S0007%20-%20huggingface-cli.md) is a command line interface distributed with the `huggingface_hub` Python package for interacting with the Hugging Face Hub. It supports account authentication, repository creation, uploading and downloading files, managing repository tags, and inspecting and deleting locally cached artifacts. [source-1](https://huggingface.co/docs/huggingface_hub/v0.24.7/guides/cli)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.CS0027 - Organization Confusion on Hugging Face](../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) — The researcher used [huggingface-cli](AML.S0007%20-%20huggingface-cli.md) to upload model artifacts containing embedded malicious code to Hugging Face repositories, making them available for users and machine learning pipelines to retrieve and execute. [ref-5stars217](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#unexpected-benefits---organization-confusion)

## Techniques implemented

- [AML.T0115.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.001%20-%20Models/README.md) — [huggingface-cli](AML.S0007%20-%20huggingface-cli.md) was used to publish model artifacts containing embedded malicious code to Hugging Face repositories through its model upload workflow. [source-2](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/)

## References

- [huggingface-cli: implementation and reporting source](https://huggingface.co/docs/huggingface_hub/v0.24.7/guides/cli)
- [Model Confusion: Weaponizing ML models for red teams and bounty hunters](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0007)
