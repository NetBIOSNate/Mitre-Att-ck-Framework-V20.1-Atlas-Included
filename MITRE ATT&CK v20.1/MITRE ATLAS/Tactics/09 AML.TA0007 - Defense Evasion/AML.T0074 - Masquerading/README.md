# AML.T0074 - Masquerading

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may attempt to manipulate features of their artifacts to make them appear legitimate or benign to users and/or security tools. Masquerading occurs when the name or location of an object, legitimate or malicious, is manipulated or abused for the sake of evading defenses and observation. This may include manipulating file metadata, tricking users into misidentifying the file type, and giving legitimate task or service names.

In public artifact registries such as HuggingFace, adversaries may reclaim or recreate a previously trusted namespace or path after it is deleted or renamed. Systems that resolve stale, unpinned identifiers may then retrieve adversary-controlled artifacts that appear to be the originally trusted artifact.

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1036](../../../../Enterprise/Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md) · [MITRE ATT&CK T1036](https://attack.mitre.org/techniques/T1036/)

## Case studies

- [AML.CS0027 - Organization Confusion on Hugging Face](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s08)
- [AML.CS0044 - LAMEHUG: Malware Leveraging Dynamic AI-Generated Commands](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md#step-s03)
- [AML.CS0049 - Supply Chain Compromise via Poisoned ClawdBot Skill](../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md#step-s09)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s08)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s03)
- [AML.CS0065 - Model Namespace Reuse Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md#step-s02)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S09](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s09)

## Mitigations

- [AML.M0011 - Restrict Library Loading](../../../Mitigations/AML.M0011%20-%20Restrict%20Library%20Loading.md) — Restrict library loading to trusted locations and approved libraries so disguised malicious libraries cannot be loaded as legitimate dependencies.
- [AML.M0025 - Maintain AI Dataset Provenance](../../../Mitigations/AML.M0025%20-%20Maintain%20AI%20Dataset%20Provenance.md) — Record dataset sources and modification history so datasets falsely presented as trusted can be identified.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0074)
