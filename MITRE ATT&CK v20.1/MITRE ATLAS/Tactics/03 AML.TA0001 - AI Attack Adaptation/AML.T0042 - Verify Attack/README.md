# AML.T0042 - Verify Attack

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Adversaries can verify the efficacy of their attack via an inference API or access to an offline copy of the target model.
This gives the adversary confidence that their approach works and allows them to carry out the attack at a later time of their choosing.
The adversary may verify the attack once but use it against many edge devices running copies of the target model.
The adversary may verify their attack digitally, then deploy it in the [Physical Environment Access](../../05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0041%20-%20Physical%20Environment%20Access/README.md) at a later time.
Verifying the attack may be hard to detect since the adversary can use a minimal number of queries or an offline copy of the model.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0000 - Evasion of Deep Learning Detector for Malware C&C Traffic](../../../Case%20Studies/Exercises/AML.CS0000%20-%20Evasion%20of%20Deep%20Learning%20Detector%20for%20Malware%20C%26C%20Traffic.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0000%20-%20Evasion%20of%20Deep%20Learning%20Detector%20for%20Malware%20C%26C%20Traffic.md#step-s04)
- [AML.CS0001 - Botnet Domain Generation Algorithm (DGA) Detection Evasion](../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md#step-s04)
- [AML.CS0010 - Microsoft Azure Service Disruption](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md#step-s06)
- [AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps](../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md#step-s05)
- [AML.CS0014 - Confusing Antimalware Neural Networks](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md#step-s07)
- [AML.CS0016 - Achieving Code Execution in MathGPT via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md#step-s03)
- [AML.CS0019 - PoisonGPT](../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md#step-s02)
- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s02)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S12](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s12)

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Obfuscating model outputs reduces an adversary's ability to verify the efficacy of an attack.
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit repeated queries used to test and refine an attack against the target model.
- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls on models at rest can prevent an adversary's ability to verify attack efficacy.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Use access controls in production to prevent adversary's ability to verify attack efficacy.
- [AML.M0040 - Adaptive AI Response Degradation](../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses to suspected attack verification queries to limit the reliability of feedback used to confirm an attack's effectiveness against the target model.

## Software implementations

- [AML.S0020 - de3u](../../../Software/Tools/AML.S0020%20-%20de3u.md) — [de3u](../../../Software/Tools/AML.S0020%20-%20de3u.md) detects and reports whether Azure OpenAI Service rejected an image-generation prompt for violating content policy. Microsoft reported that this feedback helped users develop ways to circumvent content and abuse protections. [microsoft-complaint](https://www.akingump.com/a/web/tA6v8pfayLrekvqFsLVwXT/microsoft-vs-storm-2139.pdf)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0042)
