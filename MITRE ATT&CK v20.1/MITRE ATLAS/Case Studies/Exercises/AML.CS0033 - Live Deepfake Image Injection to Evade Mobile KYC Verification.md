# AML.CS0033 - Live Deepfake Image Injection to Evade Mobile KYC Verification

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Facial biometric authentication services are commonly used by mobile applications for user onboarding, authentication, and identity verification for KYC requirements. The iProov Red Team demonstrated a face-swapped imagery injection attack that can successfully evade live facial recognition authentication models along with both passive and active [liveness verification](https://en.wikipedia.org/wiki/Liveness_test) on mobile devices. By executing this kind of attack, adversaries could gain access to privileged systems of a victim or create fake personas to create fake accounts on banking or cryptocurrency apps.

**Type**  Exercise

**Target**  Mobile facial authentication service

**Activity period**  2024

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0087 - Gather Victim Identity Information](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0087%20-%20Gather%20Victim%20Identity%20Information/README.md)

The researchers collected user identity information and high-definition facial images from online social networks and/or black-market sites.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.002 - Generative AI](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.002%20-%20Generative%20AI/README.md)

The researchers obtained [Swapface](https://swapface.org) a desktop application capable of swapping faces in a video in real-time.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.001 - Software Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.001%20-%20Software%20Tools/README.md)

The researchers obtained [Open Broadcaster Software (OBS)](https://obsproject.com) which can broadcast a video stream over the network.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016 - Obtain Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/README.md)

The researchers obtained [Virtual Camera: Live Assist](https://apkpure.com/virtual-camera-live-assist/virtual.camera.app), an Android app that allows a user to substitute the devices camera  with a video stream. This app works on genuine, non-rooted Android devices.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0088 - Generate Deepfakes](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md)

The researchers use the gathered victim face images and the Faceswap tool to produce live deepfake videos which mimic the victim's appearance.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

The researchers used the gathered victim information to register an account for a financial services application.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0047 - AI-Enabled Product or Service](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md)

During identity verification, the financial services application uses facial recognition and liveness detection to analyze live video from the user's camera.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md)

The researchers stream the deepfake video feed using OBS and use the Virtual Camera app to replace the default camera with feed. This successfully evades the facial recognition system and allows the researchers to authenticate themselves under the victim's identity.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0073 - Impersonation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0073%20-%20Impersonation/README.md)

With an authenticated account under the victim's identity, the researchers successfully impersonate the victim and evade detection.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.000 - Financial Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.000%20-%20Financial%20Harm/README.md)

The researchers could then have caused financial harm to the victim.

**Next**  End of path

## Attributed to

- [AML.E0012 - iProov Red Team](../../Entities/AML.E0012%20-%20iProov%20Red%20Team.md) (Security Evaluation)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0033)
