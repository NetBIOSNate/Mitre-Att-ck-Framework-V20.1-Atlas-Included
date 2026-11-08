# AML.M0014 - Verify AI Artifacts

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Verify the integrity and authenticity of AI artifacts before importing, loading, or deploying them. Artifacts may include model weights and checkpoints, datasets, tokenizers, model configurations, prompt templates, and agent configuration files. Verify the complete set of files used by the AI system, including supporting files that can alter model or agent behavior.

Compare cryptographic hashes against expected values obtained from an authenticated publisher. Where digital signatures or signed manifests are available, verify that they cover the artifacts being used and were produced by an authorized signer. Do not rely solely on checksums distributed alongside an artifact through the same untrusted or compromised source.

Pin approved artifacts to specific versions and cryptographic digests rather than relying on mutable names, tags, or download locations. Verify artifacts when they are acquired, transferred, or updated, and before they are loaded or interpreted.

Successful verification establishes that an artifact matches a trusted reference or was signed by an accepted identity. It does not establish that the artifact is free of malicious code, poisoned data, backdoors, or harmful instructions. Combine artifact verification with [Vulnerability Scanning](AML.M0016%20-%20Vulnerability%20Scanning.md) and [Validate AI Model](AML.M0008%20-%20Validate%20AI%20Model.md).

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Data Preparation, AI Model Engineering, AI Model Evaluation, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0010 - Supply Chain Compromise](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md) — Verify AI artifacts and associated software, data, and configuration against protected approval records before incorporating them into downstream systems.
- [AML.T0010.001 - Software](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.001%20-%20Software/README.md) — Verify software packages and supporting artifacts, including configuration files and notebooks, against approved digests or signed manifests before installation or use. Reject unauthorized substitutions or changes.
- [AML.T0010.002 - Data Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.002%20-%20Data%20Repository/README.md) — Verify datasets against protected manifests of approved versions and digests before use in training, fine-tuning, evaluation, or retrieval. Reject unauthorized substitutions or changes.
- [AML.T0010.003 - Model Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md) — Pin models to approved versions and digests, and verify all model files and bundled components before loading. Obtain expected values from authenticated sources or protected approval records.
- [AML.T0010.004 - Container Registry](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.004%20-%20Container%20Registry/README.md) — Pin container images to approved digests and verify their authenticity before deployment. Reject substitutions introduced through mutable image tags.
- [AML.T0011 - User Execution](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/README.md) — Verify artifacts against protected approval records before deserialization, loading, interpretation, or inference. Reject unauthorized changes before executable or behavior-shaping components are processed.
- [AML.T0011.000 - Unsafe AI Artifacts](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md) — Verify artifacts against protected approval records before deserialization, loading, or inference. Reject unauthorized changes before executable components are processed.
- [AML.T0018.000 - Poison AI Model](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) — Verify model weights and checkpoints against protected approval records before loading or deployment. Reject unauthorized substitutions or changes made after approval.
- [AML.T0018.001 - Modify AI Model Architecture](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.001%20-%20Modify%20AI%20Model%20Architecture/README.md) — Verify model architecture definitions against approved manifests before loading or deployment. Reject unauthorized changes even when model weights remain unchanged.
- [AML.T0018.002 - Embed Malware](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.002%20-%20Embed%20Malware/README.md) — Verify model packages against protected approval records before loading or deserialization. Reject unauthorized substitutions or changes that could introduce executable content.
- [AML.T0018.003 - Modify Prompt Construction Logic](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.003%20-%20Modify%20Prompt%20Construction%20Logic/README.md) — Verify bundled prompt templates, tokenizer configuration, embedded instructions, and tool configurations against protected approval records before interpretation. Reject unauthorized changes.
- [AML.T0020 - Training Data Poisoning](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md) — Verify training datasets and annotations against protected manifests before training. Investigate unexpected additions, removals, or changes, and update reference values only through an authorized approval process.
- [AML.T0109 - AI Supply Chain Rug Pull](../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0109%20-%20AI%20Supply%20Chain%20Rug%20Pull/README.md) — Pin dependencies and AI artifacts to approved digests and require approval and verification of each update. Prevent mutable references or automatic updates from bypassing this process.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0014)
