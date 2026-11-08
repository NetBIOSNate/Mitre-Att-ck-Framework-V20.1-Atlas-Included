# AML.S0012 - ProKYC

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[ProKYC](AML.S0012%20-%20ProKYC.md) is a tool sold for bypassing remote Know Your Customer (KYC) identity verification. It creates forged identity documents incorporating a supplied facial image, generates matching synthetic facial videos with head movements, and substitutes those videos for camera input during verification. It is marketed for fraudulent account creation on cryptocurrency exchanges. [cato](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.E0013 - ProKYC](../../Entities/AML.E0013%20-%20ProKYC.md) — [ProKYC](../../Entities/AML.E0013%20-%20ProKYC.md) used the [ProKYC](AML.S0012%20-%20ProKYC.md) tool to create fabricated identity documents and matching synthetic facial video intended to bypass remote identity verification checks. [cato](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)

## Techniques implemented

- [AML.T0088 - Generate Deepfakes](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md) — [ProKYC](AML.S0012%20-%20ProKYC.md) generates synthetic facial videos from supplied images, animating head movements to resemble a person completing a facial-verification challenge. The generated face matches the image incorporated into the forged identity document. [cato](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)

## References

- [AIID Incident 819: ProKYC Tool Allegedly Facilitates Deepfake-Based Account Fraud on Cryptocurrency Exchanges](https://incidentdatabase.ai/cite/819/)
- [Cato CTRL Threat Research: ProKYC - Deepfake Tool for Account Fraud Attacks](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0012)
