# AML.T0129 - Triggers in Multimodal Inputs

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may place instructions or triggers in one part of a multimodal input to influence the model while staying unnoticed by human reviewers and by defenses that do not inspect all input modalities.

Multimodal systems jointly process text alongside other modalities, yet many moderation and filtering controls operate mainly on the textual channel. A payload placed in a modality that is not inspected, or is inspected differently from text, is still parsed by the model but can escape detection, allowing it to alter model output or carry a cross-modal prompt injection.

Examples include instructions placed in an image, audio, or video channel, or carried in file metadata (e.g. EXIF for images, ID3 tags for audio, or document metadata).

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0008 - Validate AI Model](../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models across supported input modalities, individually and in combination, for hidden instructions or triggers that alter model behavior.
- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect supported image, audio, video, text, and metadata inputs for concealed instructions or triggers before model ingestion.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0129)
