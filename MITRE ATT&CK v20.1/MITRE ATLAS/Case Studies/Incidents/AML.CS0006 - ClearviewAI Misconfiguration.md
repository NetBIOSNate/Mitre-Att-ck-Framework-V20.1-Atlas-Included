# AML.CS0006 - ClearviewAI Misconfiguration

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Clearview AI makes a facial recognition tool that searches publicly available photos for matches.  This tool has been used for investigative purposes by law enforcement agencies and other parties.

Clearview AI's source code repository, though password protected, was misconfigured to allow an arbitrary user to register an account.
This allowed an external researcher to gain access to a private code repository that contained Clearview AI production credentials, keys to cloud storage buckets containing 70K video samples, and copies of its applications and Slack tokens.
With access to training data, a bad actor has the ability to cause an arbitrary misclassification in the deployed model.
These kinds of attacks illustrate that any attempt to secure ML system should be on top of "traditional" good cybersecurity hygiene such as locking down the system with least privileges, multi-factor authentication and monitoring and auditing.

**Type**  Incident

**Target**  Clearview AI facial recognition tool

**Activity period**  2020-04

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

A security researcher gained initial access to Clearview AI's private code repository via a misconfigured server setting that allowed an arbitrary user to register a valid account.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0036 - Data from Information Repositories](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0036%20-%20Data%20from%20Information%20Repositories/README.md)

The private code repository contained credentials which were used to access AWS S3 cloud storage buckets, leading to the discovery of assets for the facial recognition tool, including:
- Released desktop and mobile applications
- Pre-release applications featuring new capabilities
- Slack access tokens
- Raw videos and other data

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0002 - Acquire Public AI Artifacts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/README.md)

Adversaries could have downloaded training data and gleaned details about software, models, and capabilities from the source code and decompiled application binaries.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0031 - Erode AI Model Integrity](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md)

As a result, future application releases could have been compromised, causing degraded or malicious facial recognition capabilities.

**Next**  End of path

## Attributed to

- [AML.E0003 - spiderSilk](../../Entities/AML.E0003%20-%20spiderSilk.md) (Security Evaluation)

## References

- [TechCrunch Article, "Security lapse exposed Clearview AI source code"](https://techcrunch.com/2020/04/16/clearview-source-code-lapse/)
- [Gizmodo Article, "We Found Clearview AI's Shady Face Recognition App"](https://gizmodo.com/we-found-clearview-ais-shady-face-recognition-app-1841961772)
- [New York Times Article, "The Secretive Company That Might End Privacy as We Know It"](https://www.nytimes.com/2020/01/18/technology/clearview-privacy-facial-recognition.html)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0006)
