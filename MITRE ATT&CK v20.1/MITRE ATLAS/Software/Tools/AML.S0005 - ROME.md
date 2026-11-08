# AML.S0005 - ROME

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[ROME](AML.S0005%20-%20ROME.md) is an open-source implementation of Rank-One Model Editing, a method for changing individual factual associations in autoregressive language models. It applies a rank-one update to the weights of a multilayer perceptron module, aiming to make the edited association generalize across differently worded prompts while preserving unrelated factual associations. [github](https://github.com/kmeng01/rome)

**Software type**  Tool

**Aliases**  Rank-One Model Editing

**Software categories**  library

## Used by

- [AML.E0006 - Mithril Security](../../Entities/AML.E0006%20-%20Mithril%20Security.md) — [Mithril Security](../../Entities/AML.E0006%20-%20Mithril%20Security.md) used [ROME](AML.S0005%20-%20ROME.md) to modify factual associations in GPT-J, causing the model to generate targeted false information while preserving its responses to unrelated queries. [poisongpt](https://blog.mithrilsecurity.io/poisongpt-how-we-hid-a-lobotomized-llm-on-hugging-face-to-spread-fake-news/)

## Techniques implemented

- [AML.T0018.000 - Poison AI Model](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) — [ROME](AML.S0005%20-%20ROME.md) directly updates a model's multilayer perceptron weights to replace a selected factual association. Mithril Security used it to encode a false Moon-landing association in GPT-J-6B while producing little change in the model's measured ToxiGen performance. [github](https://github.com/kmeng01/rome) [mithril](https://blog.mithrilsecurity.io/poisongpt-how-we-hid-a-lobotomized-llm-on-hugging-face-to-spread-fake-news/)

## References

- [ROME: implementation and reporting source](https://github.com/kmeng01/rome)
- [PoisonGPT: How we hid a lobotomized LLM on Hugging Face to spread fake news](https://blog.mithrilsecurity.io/poisongpt-how-we-hid-a-lobotomized-llm-on-hugging-face-to-spread-fake-news/)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0005)
