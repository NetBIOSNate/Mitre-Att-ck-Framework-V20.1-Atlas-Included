# AML.CS0001 - Botnet Domain Generation Algorithm (DGA) Detection Evasion

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

The Palo Alto Networks Security AI research team was able to bypass a Convolutional Neural Network based botnet Domain Generation Algorithm (DGA) detector using a generic domain name mutation technique.
It is a generic domain mutation technique which can evade most ML-based DGA detection modules.
The generic mutation technique evades most ML-based DGA detection modules and can be used to test the effectiveness and robustness of all DGA detection methods developed by security companies in the industry before they are deployed to the production environment.

**Type**  Exercise

**Actor**  Palo Alto Networks AI Research Team

**Target**  Palo Alto Networks ML-based DGA detection module

**Activity period**  2020

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0000 - Search Open Technical Databases](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0000%20-%20Search%20Open%20Technical%20Databases/README.md)

DGA detection is a widely used technique to detect botnets in academia and industry.
The research team searched for research papers related to DGA detection.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002 - Acquire Public AI Artifacts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/README.md)

The researchers acquired a publicly available CNN-based DGA detection model and tested it against a well-known DGA generated domain name data sets, which includes ~50 million domain names from 64 botnet DGA families.
The CNN-based DGA detection model shows more than 70% detection accuracy on 16 (~25%) botnet DGA families.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.000 - Adversarial AI Attacks](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.000%20-%20Adversarial%20AI%20Attacks/README.md)

The researchers developed a generic mutation technique that requires a minimal number of iterations.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.001 - Black-Box Optimization](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md)

The researchers used the mutation technique to generate evasive domain names.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0042 - Verify Attack](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md)

The experiment results show that the detection rate of all 16 botnet DGA families drop to less than 25% after only one string is inserted once to the DGA generated domain names.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0015%20-%20Evade%20AI%20Model/README.md)

The DGA generated domain names mutated with this technique successfully evade the target DGA Detection model, allowing an adversary to continue communication with their [Command and Control](https://attack.mitre.org/tactics/TA0011/) servers.

**Next**  End of path

## References

- [Yu, Bin, Jie Pan, Jiaming Hu, Anderson Nascimento, and Martine De Cock.  "Character level based detection of DGA domain names." In 2018 International Joint Conference on Neural Networks (IJCNN), pp. 1-8. IEEE, 2018.](http://faculty.washington.edu/mdecock/papers/byu2018a.pdf)
- [Degas source code](https://github.com/matthoffman/degas)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0001)
