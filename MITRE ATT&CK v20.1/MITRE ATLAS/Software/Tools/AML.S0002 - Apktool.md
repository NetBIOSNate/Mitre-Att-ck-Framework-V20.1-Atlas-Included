# AML.S0002 - Apktool

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[Apktool](AML.S0002%20-%20Apktool.md) is an open source tool for reverse engineering Android application packages. It decodes application resources and manifests, disassembles Dalvik bytecode into smali, and extracts packaged assets for inspection and modification. It can rebuild decoded applications into APK files. [source-1](https://apktool.org/)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.CS0035 - Data Exfiltration from Slack AI via Indirect Prompt Injection](../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md) — The researchers used [Apktool](AML.S0002%20-%20Apktool.md) to unpack Android application packages and extract resource files containing compiled deep learning models. These models were then processed with DeepPayload to inject backdoors before being repackaged into the applications.[[ref-1]]

## Techniques implemented

- [AML.T0035 - AI Artifact Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md) — [Apktool](AML.S0002%20-%20Apktool.md) was used to unpack Android application packages and extract resource files containing embedded TensorFlow and TensorFlow Lite models, making the compiled models available for subsequent analysis and modification. [deep-payload](https://arxiv.org/abs/2101.06896)

## References

- [Apktool: implementation and reporting source](https://apktool.org/)
- [DeepPayload: Black-box Backdoor Attack on Deep Learning Models through Neural Payload Injection](https://arxiv.org/abs/2101.06896)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0002)
