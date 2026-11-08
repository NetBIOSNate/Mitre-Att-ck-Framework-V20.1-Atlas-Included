# AML.CS0005 - Attack on Machine Translation Services

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Machine translation services (such as Google Translate, Bing Translator, and Systran Translate) provide public-facing UIs and APIs.
A research group at UC Berkeley utilized these public endpoints to create a replicated model with near-production state-of-the-art translation quality.
Beyond demonstrating that IP can be functionally stolen from a black-box system, they used the replicated model to successfully transfer adversarial examples to the real production services.
These adversarial inputs successfully cause targeted word flips, vulgar outputs, and dropped sentences on Google Translate and Systran Translate websites.

**Type**  Exercise

**Target**  Google Translate, Bing Translator, Systran Translate

**Activity period**  2020-04-30

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0000 - Search Open Technical Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)

The researchers used published research papers to identify the datasets and model architectures used by the target translation services.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002.000 - Datasets](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.000%20-%20Datasets/README.md)

The researchers gathered similar datasets that the target translation services used.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.001%20-%20Models/README.md)

The researchers gathered similar model architectures that the target translation services used.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0135 - Outputs from AI Models](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md)

They abused a public facing application to query the model and produced machine translated sentence pairs as training data.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0005.001 - Replicate Behavior from Model Outputs](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md)

Using these translated sentence pairs, the researchers trained a model that replicates the behavior of the target model.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.004 - AI Intellectual Property Theft](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md)

By replicating the model with high fidelity, the researchers demonstrated that an adversary could steal a model and violate the victim's intellectual property rights.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.002 - Black-Box Transfer](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.002%20-%20Black-Box%20Transfer/README.md)

The replicated models were used to generate adversarial examples that successfully transferred to the black-box translation services.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0015%20-%20Evade%20AI%20Model/README.md)

The adversarial examples were used to evade the machine translation services by a variety of means. This included targeted word flips, vulgar outputs, and dropped sentences.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0031 - Erode AI Model Integrity](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md)

Adversarial attacks can cause errors that cause reputational damage to the company of the translation service and decrease user trust in AI-powered services.

**Next**  End of path

## Attributed to

- [AML.E0004 - Berkeley Artificial Intelligence Research](../../Entities/AML.E0004%20-%20Berkeley%20Artificial%20Intelligence%20Research.md) (Security Evaluation)

## References

- [Wallace, Eric, et al. "Imitation Attacks and Defenses for Black-box Machine Translation Systems" EMNLP 2020](https://arxiv.org/abs/2004.15015)
- [Project Page, "Imitation Attacks and Defenses for Black-box Machine Translation Systems"](https://www.ericswallace.com/imitation)
- [Google under fire for mistranslating Chinese amid Hong Kong protests](https://thehill.com/policy/international/asia-pacific/449164-google-under-fire-for-mistranslating-chinese-amid-hong-kong/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0005)
