# AML.E0028 - Skyld

[MITRE ATLAS](../README.md) / [Entities](README.md)

[Skyld](AML.E0028%20-%20Skyld.md) is a French AI security company founded in July 2023. They develop approaches to protect AI models against theft, reverse engineering, and adversarial manipulation. Their work combines cryptography and AI security to protect the confidentiality and integrity of models deployed in unsecured environments. [group-profile](https://skyld.io/company/about-us/)

**Entity type**  Organization

## Uses

- [AML.S0021 - Frida](../Software/Tools/AML.S0021%20-%20Frida.md) — [Skyld](AML.E0028%20-%20Skyld.md) researchers used custom [Frida](../Software/Tools/AML.S0021%20-%20Frida.md) scripts to hook the model-decryption process in Google Photos on Android and capture decrypted TensorFlow Lite models as they were loaded into memory. This recovered 20 models protected by encryption at rest. [software-evidence](https://skyld.io/google-photos-model-extraction)

## Attributed case studies

- [AML.CS0058 - Google Photos AI Model Extraction](../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md) (Security Evaluation)

## References

- [About Skyld](https://skyld.io/company/about-us/)
- [Google Photos AI Models: The Secret Sauce That Can Be Stolen](https://skyld.io/google-photos-model-extraction)

[Official ATLAS record](https://atlas.mitre.org/entities/AML.E0028)
