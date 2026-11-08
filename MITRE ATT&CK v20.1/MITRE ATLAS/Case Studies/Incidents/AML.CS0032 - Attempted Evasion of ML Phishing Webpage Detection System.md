# AML.CS0032 - Attempted Evasion of ML Phishing Webpage Detection System

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Adversaries create phishing websites that appear visually similar to legitimate sites. These sites are designed to trick users into entering their credentials, which are then sent to the bad actor. To combat this behavior, security companies utilize AI/ML-based approaches to detect phishing sites and block them in their endpoint security products.

In this incident, adversarial examples were identified in the logs of a commercial machine learning phishing website detection system. The detection system makes an automated block/allow determination from the "phishing score" of an ensemble of image classifiers each responsible for different phishing indicators (visual similarity, input form detection, etc.). The adversarial examples appeared to employ several simple yet effective strategies for manually modifying brand logos in an attempt to evade image classification models. The phishing websites which employed logo modification methods successfully evaded the model responsible detecting brand impersonation via visual similarity. However, the other components of the system successfully flagged the phishing websites.

**Type**  Incident

**Actor**  Unknown

**Target**  Commercial ML Phishing Webpage Detector

**Reporter**  Norton Research Group (NRG)

**Activity period**  2022-12

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043.003 - Manual Modification](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.003%20-%20Manual%20Modification/README.md)

Several cheap, yet effective strategies for manually modifying logos were observed:
| Evasive Strategy | Count |
| - | - |
| Company name style | 25 |
| Blurry logo | 23 |
| Cropping | 20 |
| No company name | 16 |
| No visual logo | 13 |
| Different visual logo | 12 |
| Logo stretching | 11 |
| Multiple forms - images | 10 |
| Background patterns | 8 |
| Login obfuscation | 6 |
| Masking | 3 |

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0015 - Evade AI Model](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0015%20-%20Evade%20AI%20Model/README.md)

The visual similarity model used to detect brand impersonation was evaded. However, other components of the phishing detection system successfully identified the phishing websites.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0052 - Phishing](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md)

If the adversary can successfully evade detection, they can continue to operate their phishing websites and steal the victim's credentials.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

The end user may experience a variety of harms including financial and privacy harms depending on the credentials stolen by the adversary.

**Next**  End of path

## References

- ["Real Attackers Don't Compute Gradients": Bridging the Gap Between Adversarial ML Research and Practice](https://arxiv.org/abs/2212.14315)
- [Real Attackers Don't Compute Gradients Supplementary Resources](https://real-gradients.github.io/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0032)
