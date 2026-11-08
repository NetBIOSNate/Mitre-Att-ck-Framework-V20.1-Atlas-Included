# AML.CS0034 - ProKYC: Deepfake Tool for Account Fraud Attacks

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Cato CTRL security researchers have identified ProKYC, a deepfake tool being sold to cybercriminals as a method to bypass Know Your Customer (KYC) verification on financial service applications such as cryptocurrency exchanges. ProKYC can create fake identity documents and generate deepfake selfie videos, two key pieces of biometric data used during KYC verification. The tool helps cybercriminals defeat facial recognition and liveness checks to create fraudulent accounts.

The procedure below describes how a bad actor could use ProKYC's service to bypass KYC verification.

**Type**  Incident

**Target**  KYC verification services

**Reporter**  Cato CTRL

**Activity period**  2024-10-09

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0087 - Gather Victim Identity Information](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0087%20-%20Gather%20Victim%20Identity%20Information/README.md)

The bad actor collected user identity information.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.002 - Generative AI](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.002%20-%20Generative%20AI/README.md)

The bad actor paid for the ProKYC tool, created a fake identity document, generated a deepfake selfie video, and replaced a live camera feed with the deepfake video.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0088 - Generate Deepfakes](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md)

The bad actor used a mixture of real PII and falsified details with the ProKYC tool to generate a deepfaked identity document.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0088 - Generate Deepfakes](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md)

The bad actor used ProKYC tool to generate a deepfake selfie video with the same face as the identity document designed to bypass liveness checks.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

The bad actor used the victim information to register an account with a financial services application, such as a cryptocurrency exchange.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0047 - AI-Enabled Product or Service](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md)

During identity verification, the financial services application used facial recognition and liveness detection to analyze live video from the user's camera.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md)

The bad actor used ProKYC to replace the camera feed with the deepfake selfie video. This successfully evaded the KYC verification and allowed the bad actor to authenticate themselves under the false identity.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0073 - Impersonation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0073%20-%20Impersonation/README.md)

With an authenticated account under the victim's identity, the bad actor successfully impersonated the victim and evaded detection.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.000 - Financial Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.000%20-%20Financial%20Harm/README.md)

The bad actor used this access to cause financial harm to the victim.

**Next**  End of path

## Attributed to

- [AML.E0013 - ProKYC](../../Entities/AML.E0013%20-%20ProKYC.md) (Adversarial Operation)

## Reported by

- [AML.E0016 - Cato Networks](../../Entities/AML.E0016%20-%20Cato%20Networks.md)

## References

- [AIID Incident 819: ProKYC Tool Allegedly Facilitates Deepfake-Based Account Fraud on Cryptocurrency Exchanges](https://incidentdatabase.ai/cite/819/)
- [Cato CTRL Threat Research: ProKYC - Deepfake Tool for Account Fraud Attacks](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)
- [ProKYC: Synthetic Identity Fraud as a Service](https://idscan.net/blog/prokyc-synthetic-identity-fraud/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0034)
