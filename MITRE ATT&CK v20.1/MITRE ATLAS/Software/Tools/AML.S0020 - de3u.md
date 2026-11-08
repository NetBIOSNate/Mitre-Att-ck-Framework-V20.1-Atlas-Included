# AML.S0020 - de3u

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[de3u](AML.S0020%20-%20de3u.md) is a client-side application for generating images with DALL-E through Azure OpenAI Service. It provides controls for text prompts, API credentials, proxy connections, and image-generation settings. Microsoft describes features designed to prevent automatic prompt revision and report content-policy rejections, supporting attempts to circumvent the service's safeguards. [microsoft-complaint](https://www.akingump.com/a/web/tA6v8pfayLrekvqFsLVwXT/microsoft-vs-storm-2139.pdf)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.E0027 - Storm-2139](../../Entities/AML.E0027%20-%20Storm-2139.md) — [Storm-2139](../../Entities/AML.E0027%20-%20Storm-2139.md) developed and operated [de3u](AML.S0020%20-%20de3u.md) as part of its unauthorized generative AI access and content generation service. [group-profile](https://blogs.microsoft.com/on-the-issues/2025/02/27/disrupting-cybercrime-abusing-gen-ai/)

## Techniques implemented

- [AML.T0042 - Verify Attack](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md) — [de3u](AML.S0020%20-%20de3u.md) detects and reports whether Azure OpenAI Service rejected an image-generation prompt for violating content policy. Microsoft reported that this feedback helped users develop ways to circumvent content and abuse protections. [microsoft-complaint](https://www.akingump.com/a/web/tA6v8pfayLrekvqFsLVwXT/microsoft-vs-storm-2139.pdf)
- [AML.T0054 - LLM Jailbreak](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0054%20-%20LLM%20Jailbreak/README.md) — [de3u](AML.S0020%20-%20de3u.md) includes functionality designed to prevent Azure OpenAI Service from revising submitted image-generation prompts. Microsoft identified this functionality, together with content-policy rejection feedback, as supporting circumvention of the service's content safeguards. [microsoft-complaint](https://www.akingump.com/a/web/tA6v8pfayLrekvqFsLVwXT/microsoft-vs-storm-2139.pdf)
- [AML.T0088 - Generate Deepfakes](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md) — According to Microsoft, users employed [de3u](AML.S0020%20-%20de3u.md) to submit image-generation requests to DALL-E through Azure OpenAI Service and generate non-consensual intimate images of celebrities. [microsoft-complaint](https://www.akingump.com/a/web/tA6v8pfayLrekvqFsLVwXT/microsoft-vs-storm-2139.pdf)

## References

- [Disrupting a global cybercrime network abusing generative AI](https://blogs.microsoft.com/on-the-issues/2025/02/27/disrupting-cybercrime-abusing-gen-ai/)
- [Microsoft v. Storm-2139 - Proposed Amended Complaint, Document 39-1, February 27, 2025](https://www.akingump.com/a/web/tA6v8pfayLrekvqFsLVwXT/microsoft-vs-storm-2139.pdf)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0020)
