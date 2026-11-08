# AML.CS0031 - Malicious Models on Hugging Face

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers at ReversingLabs have identified malicious models containing embedded malware hosted on the Hugging Face model repository. The models were found to execute reverse shells when loaded, which grants the threat actor command and control capabilities on the victim's system. Hugging Face uses Picklescan to scan models for malicious code, however these models were not flagged as malicious. The researchers discovered that the model files were seemingly purposefully corrupted in a way that the malicious payload is executed before the model ultimately fails to de-serialize fully. Picklescan relied on being able to fully de-serialize the model.

Since becoming aware of this issue, Hugging Face has removed the models and has made changes to Picklescan to catch this particular attack. However, pickle files are fundamentally unsafe as they allow for arbitrary code execution, and there may be other types of malicious pickles that Picklescan cannot detect.

**Type**  Incident

**Actor**  Unknown

**Target**  Hugging Face users

**Reporter**  ReversingLabs

**Activity period**  2025

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0018.002 - Embed Malware](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.002%20-%20Embed%20Malware/README.md)

The adversary embedded malware into an AI model stored in a pickle file. The malware was designed to execute when the model is loaded by a user.

ReversingLabs found two instances of this on Hugging Face during their research.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0115.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.001%20-%20Models/README.md)

The adversary uploaded the model to Hugging Face.

In both instances observed by the ReversingLab, the malicious models did not make any attempt to mimic a popular legitimate model.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0076 - Corrupt AI Model](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0076%20-%20Corrupt%20AI%20Model/README.md)

The adversary evaded detection by [Picklescan](https://github.com/mmaitre314/picklescan), which Hugging Face uses to flag malicious models. This occurred because the model could not be fully deserialized.

In their analysis, the ReversingLabs researchers found that the malicious payload was still executed.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010 - Supply Chain Compromise](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md)

Because the models were successfully uploaded to Hugging Face, a user relying on this model repository would have their supply chain compromised.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.000 - Unsafe AI Artifacts](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md)

If a user loaded the malicious model, the adversary's malicious payload is executed.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0014 - Command and Control](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/README.md) / [AML.T0072 - Cyber Communication Channel](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0072%20-%20Cyber%20Communication%20Channel/README.md)

The malicious payload was a reverse shell set to connect to a hardcoded IP address.

**Next**  End of path

## References

- [Malicious ML models discovered on Hugging Face platform](https://www.reversinglabs.com/blog/rl-identifies-malware-ml-model-hosted-on-hugging-face?&web_view=true)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0031)
