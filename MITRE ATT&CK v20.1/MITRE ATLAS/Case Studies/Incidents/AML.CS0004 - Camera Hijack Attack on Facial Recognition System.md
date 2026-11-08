# AML.CS0004 - Camera Hijack Attack on Facial Recognition System

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

This type of camera hijack attack can evade the traditional live facial recognition authentication model and enable access to privileged systems and victim impersonation.

Two individuals in China used this attack to gain access to the local government's tax system. They created a fake shell company and sent invoices via tax system to supposed clients. The individuals started this scheme in 2018 and were able to fraudulently collect $77 million.

**Type**  Incident

**Actor**  Two individuals

**Target**  Shanghai government tax office's facial recognition service

**Reporter**  Ant Group AISEC Team

**Activity period**  2020

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0087 - Gather Victim Identity Information](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0087%20-%20Gather%20Victim%20Identity%20Information/README.md)

The attackers collected user identity information and high-definition face photos from an online black market.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

The attackers used the victim identity information to register new accounts in the tax system.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.001 - Consumer Hardware](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.001%20-%20Consumer%20Hardware/README.md)

The attackers bought customized low-end mobile phones.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.001 - Software Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.001%20-%20Software%20Tools/README.md)

The attackers obtained customized Android ROMs and a virtual camera application.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.000 - Adversarial AI Attack Implementations](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.000%20-%20Adversarial%20AI%20Attack%20Implementations/README.md)

The attackers obtained software that turns static photos into videos, adding realistic effects such as blinking eyes.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0047 - AI-Enabled Product or Service](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md)

The attackers used the virtual camera app to present the generated video to the ML-based facial recognition service used for user verification.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md)

The attackers successfully evaded the face recognition system. This allowed the attackers to impersonate the victim and verify their identity in the tax system.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.000 - Financial Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.000%20-%20Financial%20Harm/README.md)

The attackers used their privileged access to the tax system to send invoices to supposed clients and further their fraud scheme.

**Next**  End of path

## References

- [Faces are the next target for fraudsters](https://www.wsj.com/articles/faces-are-the-next-target-for-fraudsters-11625662828)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0004)
