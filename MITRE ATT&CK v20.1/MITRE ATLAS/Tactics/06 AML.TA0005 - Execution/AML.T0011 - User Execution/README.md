# AML.T0011 - User Execution

[MITRE ATLAS](../../../README.md) / [AML.TA0005 - Execution](../README.md)

An adversary may rely upon a user to load, execute, interpret, or otherwise use a malicious or unsafe artifact. In AI systems, user execution may include loading a model or causing an inference runtime to process executable or behavior-shaping components bundled with an AI artifact. The resulting effect may include host code execution or malicious AI behavior.

Users may inadvertently execute unsafe code introduced via [Supply Chain Compromise](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md).

Users may be subjected to social engineering to get them to execute malicious code by, for example, opening a malicious document file or link.

**Tactics**  [AML.TA0005 - Execution](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0011.003 - Malicious Link](AML.T0011.003%20-%20Malicious%20Link/README.md)
- [AML.T0011.001 - Malicious Package](AML.T0011.001%20-%20Malicious%20Package/README.md)
- [AML.T0011.002 - Poisoned AI Agent Tool](AML.T0011.002%20-%20Poisoned%20AI%20Agent%20Tool/README.md)
- [AML.T0011.000 - Unsafe AI Artifacts](AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md)

## Case studies

- [AML.CS0018 - Arbitrary Code Execution with Google Colab](../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md#step-s03)
- [AML.CS0044 - LAMEHUG: Malware Leveraging Dynamic AI-Generated Commands](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md#step-s04)
- [AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md#step-s05)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S16](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s16)

## Mitigations

- [AML.M0011 - Restrict Library Loading](../../../Mitigations/AML.M0011%20-%20Restrict%20Library%20Loading.md) — Restricting binaries from loading external libraries can limit their ability to execute malicious code.
- [AML.M0014 - Verify AI Artifacts](../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify artifacts against protected approval records before deserialization, loading, interpretation, or inference. Reject unauthorized changes before executable or behavior-shaping components are processed.
- [AML.M0016 - Vulnerability Scanning](../../../Mitigations/AML.M0016%20-%20Vulnerability%20Scanning.md) — Vulnerability scanning can help identify malicious binaries and prevent user execution.
- [AML.M0018 - User Training](../../../Mitigations/AML.M0018%20-%20User%20Training.md) — Training users to be able to identify attempts at manipulation will make them less susceptible to performing techniques that cause the execution of malicious code.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0011)
