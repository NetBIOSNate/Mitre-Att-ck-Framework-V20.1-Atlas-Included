# AML.CS0007 - GPT-2 Model Replication

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

OpenAI built GPT-2, a language model capable of generating high quality text samples. Over concerns that GPT-2 could be used for malicious purposes such as impersonating others, or generating misleading news articles, fake social media content, or spam, OpenAI adopted a tiered release schedule. They initially released a smaller, less powerful version of GPT-2 along with a technical description of the approach, but held back the full trained model.

Before the full model was released by OpenAI, researchers at Brown University successfully replicated the model using information released by OpenAI and open source ML artifacts. This demonstrates that a bad actor with sufficient technical skill and compute resources could have replicated GPT-2 and used it for harmful goals before the AI Security community is prepared.

**Type**  Exercise

**Actor**  Researchers at Brown University

**Target**  OpenAI GPT-2

**Activity period**  2019-08-22

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0000 - Search Open Technical Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)

Using the public documentation about GPT-2, the researchers gathered information about the dataset, model architecture, and training hyper-parameters.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.001%20-%20Models/README.md)

The researchers obtained a reference implementation of a similar publicly available model called Grover.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002.000 - Datasets](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.000%20-%20Datasets/README.md)

The researchers were able to manually recreate the dataset used in the original GPT-2 paper using the gathered documentation.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.000 - AI Development Workspaces](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.000%20-%20AI%20Development%20Workspaces/README.md)

The researchers were able to use TensorFlow Research Cloud via their academic credentials.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0005.000 - Replicate Behavior from Gathered AI Artifacts](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.000%20-%20Replicate%20Behavior%20from%20Gathered%20AI%20Artifacts/README.md)

The researchers modified Grover's objective function to reflect GPT-2's objective function and then trained on the dataset they curated using used Grover's initial hyperparameters. The resulting model functionally replicates GPT-2, obtaining similar performance on most datasets.
A bad actor who followed the same procedure as the researchers could then use the replicated GPT-2 model for malicious purposes.

**Next**  End of path

## References

- [Wired Article, "OpenAI Said Its Code Was Risky. Two Grads Re-Created It Anyway"](https://www.wired.com/story/dangerous-ai-open-source/)
- [Medium BlogPost, "OpenGPT-2: We Replicated GPT-2 Because You Can Too"](https://blog.usejournal.com/opengpt-2-we-replicated-gpt-2-because-you-can-too-45e34e6d36dc)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0007)
