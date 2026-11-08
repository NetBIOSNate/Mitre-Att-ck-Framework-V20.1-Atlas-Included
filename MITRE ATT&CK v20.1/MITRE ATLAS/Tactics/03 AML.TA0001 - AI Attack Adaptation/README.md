# AML.TA0001 - AI Attack Adaptation

[MITRE ATLAS](../../README.md) / [Tactics](../README.md)

The adversary is adapting capabilities, methods, knowledge, or objectives into attack-ready outputs for a target or current operational conditions.

[AI Attack Adaptation](README.md) consists of techniques adversaries use to transform reusable capabilities, general attack methods, target knowledge, high-level objectives, and operational observations into target- or context-specific attack-ready outputs. Adaptation may target an AI system directly, or it may use an AI capability to materially shape malicious content for attacks against AI components, software, infrastructure, people, or other systems. Adapted outputs may include proxy or manipulated models, adversarial data, crafted prompts or retrieval content, deepfakes, or generated malicious commands or code. Outputs can also include actions for an autonomous agent such as agent tasking, high-level objectives, action sequences, and tool instructions.

AI Attack Adaptation may occur before [Initial Access](../04%20AML.TA0004%20-%20Initial%20Access/README.md) is achieved and repeatedly throughout an operation. Adversaries may use knowledge obtained through [Reconnaissance](../01%20AML.TA0002%20-%20Reconnaissance/README.md) or [Discovery](../11%20AML.TA0008%20-%20Discovery/README.md), access obtained through [AI Model Access](../05%20AML.TA0000%20-%20AI%20Model%20Access/README.md), and capabilities established through [Resource Development](../02%20AML.TA0003%20-%20Resource%20Development/README.md). [Resource Development](../02%20AML.TA0003%20-%20Resource%20Development/README.md) creates or obtains reusable capabilities whereas [AI Attack Adaptation](README.md) applies or modifies those capabilities for a target, objective, or current operational condition.

## Techniques

- [AML.T0118 - Autonomous AI Agent Communication](AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/README.md)
- [AML.T0124 - Autonomous Attack Orchestration](AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md)
- [AML.T0117 - Autonomous Attack-Path Adaptation](AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md)
- [AML.T0043 - Craft Adversarial Data](AML.T0043%20-%20Craft%20Adversarial%20Data/README.md)
- [AML.T0088 - Generate Deepfakes](AML.T0088%20-%20Generate%20Deepfakes/README.md)
- [AML.T0102 - Generate Malicious Commands](AML.T0102%20-%20Generate%20Malicious%20Commands/README.md)
- [AML.T0065 - LLM Prompt Crafting](AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)
- [AML.T0018 - Manipulate AI Model](AML.T0018%20-%20Manipulate%20AI%20Model/README.md)
- [AML.T0005 - Replicate AI Model Behavior](AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md)
- [AML.T0066 - Retrieval Content Crafting](AML.T0066%20-%20Retrieval%20Content%20Crafting/README.md)
- [AML.T0042 - Verify Attack](AML.T0042%20-%20Verify%20Attack/README.md)

[Official ATLAS record](https://atlas.mitre.org/tactics/AML.TA0001)
