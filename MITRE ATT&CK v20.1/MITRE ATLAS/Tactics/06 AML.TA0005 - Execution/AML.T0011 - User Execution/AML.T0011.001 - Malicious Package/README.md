# AML.T0011.001 - Malicious Package

[MITRE ATLAS](../../../../README.md) / [AML.TA0005 - Execution](../../README.md) / [AML.T0011 - User Execution](../README.md)

Adversaries may develop malicious software packages that when imported by a user have a deleterious effect.
Malicious packages may behave as expected to the user. They may be introduced via [Supply Chain Compromise](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md). They may not present as obviously malicious to the user and may appear to be useful for an AI-related task.

**Tactics**  [AML.TA0005 - Execution](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0022 - ChatGPT Package Hallucination](../../../../Case%20Studies/Exercises/AML.CS0022%20-%20ChatGPT%20Package%20Hallucination.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0022%20-%20ChatGPT%20Package%20Hallucination.md#step-s04)
- [AML.CS0047 - Code to Deploy Destructive AI Agent Discovered in Amazon Q VS Code Extension](../../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md) · [S03](../../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md#step-s03)

## Mitigations

- [AML.M0011 - Restrict Library Loading](../../../../Mitigations/AML.M0011%20-%20Restrict%20Library%20Loading.md) — Restricting packages from loading external libraries can limit their ability to execute malicious code.
- [AML.M0013 - Code Signing](../../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Code signing provides a guarantee that the software package has not been manipulated after signing took place.
- [AML.M0016 - Vulnerability Scanning](../../../../Mitigations/AML.M0016%20-%20Vulnerability%20Scanning.md) — Vulnerability scanning can help identify malicious packages and prevent user execution.
- [AML.M0018 - User Training](../../../../Mitigations/AML.M0018%20-%20User%20Training.md) — Train users to identify attempts of manipulation to prevent them from running unsafe code from external packages.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0011.001)
