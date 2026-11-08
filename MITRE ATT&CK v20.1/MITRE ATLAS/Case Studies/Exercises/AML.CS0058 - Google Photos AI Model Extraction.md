# AML.CS0058 - Google Photos AI Model Extraction

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Skyld researchers analyzed the Google Photos Android application and recovered TensorFlow Lite models used by AI-powered photo editing and image analysis features. The researchers found models stored unencrypted in the application's assets, embedded in the native library, and encrypted on disk. They used static reverse engineering to locate TFLite artifacts and dynamic instrumentation with Frida to capture encrypted models after runtime decryption. The recovered models provided white-box access to proprietary Google Photos model artifacts.

**Type**  Exercise

**Target**  Google Photos Android App

**Activity period**  2025-03

## Procedure steps

### Step S00

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0007 - Discover AI Artifacts](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0007%20-%20Discover%20AI%20Artifacts/README.md)

Skyld researchers analyzed the Google Photos Android Package (APK) and identified TensorFlow Lite as the machine learning framework used by the app. They searched the application package and native libraries for TFLite artifacts using the TFL3 file identifier.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0035 - AI Artifact Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md)

The researchers collected TensorFlow Lite model artifacts from multiple locations in the APK, including unencrypted assets, files embedded in the native library, and application-specific folders.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

The researchers used static analysis and Frida instrumentation to recover model files. For encrypted models, they intercepted decrypted TFLite files during runtime as Google Photos loaded them for execution.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0044 - Full AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0044%20-%20Full%20AI%20Model%20Access/README.md)

Exfiltrating model files from the APK gave the researchers full access to the Google Photos AI models, including those used for tasks such as face detection, object detection, segmentation, depth estimation, image quality assessment, and blur detection.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.000 - White-Box Optimization](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.000%20-%20White-Box%20Optimization/README.md)

The recovered TensorFlow Lite models could enable white-box adversarial example generation.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0015%20-%20Evade%20AI%20Model/README.md)

Adversarial data could be used to evade or otherwise degrade the Google Photos models including face and object detection.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.004 - AI Intellectual Property Theft](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md)

The recovered models represented proprietary Google Photos AI assets. An adversary or competitor could use the extracted models to study, reuse, or replicate Google Photos capabilities, reducing the cost of independently developing similar features.

**Next**  End of path

## Attributed to

- [AML.E0028 - Skyld](../../Entities/AML.E0028%20-%20Skyld.md) (Security Evaluation)

## References

- [Google Photos AI Models: The Secret Sauce That Can Be Stolen](https://skyld.io/google-photos-model-extraction)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0058)
