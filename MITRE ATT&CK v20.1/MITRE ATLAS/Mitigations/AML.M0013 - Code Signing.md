# AML.M0013 - Code Signing

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Enforce binary and application integrity with digital signature verification to prevent untrusted code from executing. Adversaries can embed malicious code in AI software or models. Developers should also cryptographically sign SBOM and AIBOM components that track model or data provenance. Enforcement of code signing can prevent the compromise of the AI supply chain and prevent execution of malicious code.

**ATT&CK mapping**  [Local ATT&CK M1045](../../Enterprise/Defenses/Mitigations/M1045%20-%20Code%20Signing.md) · [MITRE ATT&CK M1045](https://attack.mitre.org/mitigations/M1045/)

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Deployment

## Techniques mitigated

- [AML.T0010.001 - Software](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.001%20-%20Software/README.md) — Enforce properly signed drivers and ML software frameworks.
- [AML.T0010.003 - Model Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md) — Enforce properly signed model files.
- [AML.T0011.000 - Unsafe AI Artifacts](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md) — Prevent execution of ML artifacts that are not properly signed.
- [AML.T0011.001 - Malicious Package](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.001%20-%20Malicious%20Package/README.md) — Code signing provides a guarantee that the software package has not been manipulated after signing took place.
- [AML.T0018 - Manipulate AI Model](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/README.md) — Code signing provides a guarantee that the model has not been manipulated after signing took place.
- [AML.T0018.000 - Poison AI Model](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) — Code signing provides a guarantee that the model has not been manipulated after signing took place.
- [AML.T0018.001 - Modify AI Model Architecture](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.001%20-%20Modify%20AI%20Model%20Architecture/README.md) — Code signing provides a guarantee that the model has not been manipulated after signing took place.
- [AML.T0018.002 - Embed Malware](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.002%20-%20Embed%20Malware/README.md) — Code signing provides a guarantee that the model has not been manipulated after signing took place.
- [AML.T0103 - Deploy AI Agent](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0103%20-%20Deploy%20AI%20Agent/README.md) — Allow only trusted signed agent applications to execute in the environment.
- [AML.T0142 - Event Triggered Execution](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0142%20-%20Event%20Triggered%20Execution/README.md) — Enforce that all software packages be signed before execution.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0013)
