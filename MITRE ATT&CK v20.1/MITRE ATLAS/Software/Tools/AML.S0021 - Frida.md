# AML.S0021 - Frida

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[Frida](AML.S0021%20-%20Frida.md) is an open source dynamic instrumentation toolkit for inspecting and modifying running applications without their source code. It supports injecting scripts into processes, intercepting function calls, and tracing application behavior. Frida provides command line tools and language bindings and supports platforms including Windows, macOS, Linux, Android, and iOS. [source-1](https://frida.re/)

**Software type**  Tool

**Software categories**  program, library

## Used by

- [AML.E0028 - Skyld](../../Entities/AML.E0028%20-%20Skyld.md) — [Skyld](../../Entities/AML.E0028%20-%20Skyld.md) researchers used custom [Frida](AML.S0021%20-%20Frida.md) scripts to hook the model-decryption process in Google Photos on Android and capture decrypted TensorFlow Lite models as they were loaded into memory. This recovered 20 models protected by encryption at rest. [software-evidence](https://skyld.io/google-photos-model-extraction)

## Techniques implemented

- [AML.T0035 - AI Artifact Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md) — [Frida](AML.S0021%20-%20Frida.md) was used to intercept Google Photos' model-decryption process and capture decrypted TensorFlow Lite models as they were loaded into memory, recovering model artifacts protected by encryption at rest. [skyld](https://skyld.io/google-photos-model-extraction)

## References

- [Frida](https://frida.re/)
- [Google Photos AI Models: The Secret Sauce That Can Be Stolen](https://skyld.io/google-photos-model-extraction)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0021)
