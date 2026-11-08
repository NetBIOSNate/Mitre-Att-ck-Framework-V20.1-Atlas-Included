# AML.S0006 - EasyEdit

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[EasyEdit](AML.S0006%20-%20EasyEdit.md) is an open source Python framework for editing knowledge and behavior in language and multimodal models. It provides implementations of methods including ROME, MEMIT, and MEND, with shared interfaces for configuring edits and evaluating their effectiveness, generalization, and effects on unrelated outputs. Its tooling supports targeted model changes without retraining the entire model. [github](https://github.com/zjunlp/EasyEdit)

**Software type**  Tool

**Software categories**  library

## Used by

- [AML.CS0027 - Organization Confusion on Hugging Face](../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) — The researcher used [EasyEdit](AML.S0006%20-%20EasyEdit.md) with the MEND editing method to target a factual association in Llama-2-7b, specifying Sydney instead of Canberra as the desired answer to a question about Australia's capital. [ref-5stars217](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#unexpected-benefits---organization-confusion)

## Techniques implemented

- [AML.T0018.000 - Poison AI Model](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) — [EasyEdit](AML.S0006%20-%20EasyEdit.md) provides model editing methods that update selected model parameters to change factual associations or other targeted behavior. [github](https://github.com/zjunlp/EasyEdit)

## References

- [Model Confusion: Weaponizing ML models for red teams and bounty hunters](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/)
- [EasyEdit GitHub](https://github.com/zjunlp/EasyEdit)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0006)
