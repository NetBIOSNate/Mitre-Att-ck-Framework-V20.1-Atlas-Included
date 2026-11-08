# AML.CS0027 - Organization Confusion on Hugging Face

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

[threlfall_hax](https://5stars217.github.io/), a security researcher, created organization accounts on Hugging Face, a public model repository, that impersonated real organizations. These false Hugging Face organization accounts looked legitimate so individuals from the impersonated organizations requested to join, believing the accounts to be an official site for employees to share models. This gave the researcher full access to any AI models uploaded by the employees, including the ability to replace models with malicious versions. The researcher demonstrated that they could embed malware into an AI model that provided them access to the victim organization's environment. From there, threat actors could execute a range of damaging attacks such as intellectual property theft or poisoning other AI models within the victim's environment.

**Type**  Exercise

**Actor**  threlfall_hax

**Target**  Hugging Face users

**Activity period**  2023-08-23

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

The researcher registered an unverified "organization" account on Hugging Face that squats on the namespace of a targeted company.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0073 - Impersonation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0073%20-%20Impersonation/README.md)

Employees of the targeted company found and joined the fake Hugging Face organization. Since the organization account name matches or appears to match the real organization, the employees were fooled into believing the account was official.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0044 - Full AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0044%20-%20Full%20AI%20Model%20Access/README.md)

The employees made use of the Hugging Face organization and uploaded private models. As owner of the Hugging Face account, the researcher has full read and write access to all of these uploaded models.

**Next**  [S03](#step-s03), [S04](#step-s04)

### Step S03

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.004 - AI Intellectual Property Theft](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md)

With full access to the model, an adversary could steal valuable intellectual property in the form of AI models.

**Next**  End of path

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0018.002 - Embed Malware](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.002%20-%20Embed%20Malware/README.md)

The researcher embedded [Sliver](https://github.com/BishopFox/sliver), an open source C2 server, into the target model. They added a `Lambda` layer to the model, which allows for arbitrary code to be run, and used an `exec()` call to execute the Sliver payload.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0115.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.001%20-%20Models/README.md)

The researcher re-uploaded the manipulated model to the Hugging Face repository.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.003 - Model Repository](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md)

The victim's AI model supply chain is now compromised. Users of the model repository will receive the adversary's model with embedded malware.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.000 - Unsafe AI Artifacts](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md)

When any future user loads the model, the model automatically executes the adversary's payload.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0074 - Masquerading](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0074%20-%20Masquerading/README.md)

The researcher named the Sliver process `training.bin` to disguise it as a legitimate model training process. Furthermore, the model still operates as normal, making it less likely a user will notice something is wrong.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0014 - Command and Control](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/README.md) / [AML.T0072 - Cyber Communication Channel](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0072%20-%20Cyber%20Communication%20Channel/README.md)

The Sliver implant grants the researcher a command and control channel so they can explore the victim's environment and continue the attack.

**Next**  [S10](#step-s10), [S12](#step-s12)

### Step S10

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

The researcher checked environment variables and searched Jupyter notebooks for API keys and other secrets.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

Discovered credentials could be exfiltrated via the Sliver implant.

**Next**  End of path

### Step S12

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0007 - Discover AI Artifacts](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0007%20-%20Discover%20AI%20Artifacts/README.md)

The researcher could have searched for AI models in the victim organization's environment.

**Next**  [S13](#step-s13)

### Step S13

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.000 - Adversarial AI Attack Implementations](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.000%20-%20Adversarial%20AI%20Attack%20Implementations/README.md)

The researcher obtained [EasyEdit](https://github.com/zjunlp/EasyEdit), an open-source knowledge editing tool for large language models.

**Next**  [S14](#step-s14)

### Step S14

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0018.000 - Poison AI Model](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md)

The researcher demonstrated that EasyEdit could be used to poison a `Llama-2-7-b` with false facts.

**Next**  [S15](#step-s15)

### Step S15

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048 - External Harms](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/README.md)

If the company's models were manipulated to produce false information, a variety of harms including financial and reputational could occur.

**Next**  End of path

## Uses

- [AML.S0006 - EasyEdit](../../Software/Tools/AML.S0006%20-%20EasyEdit.md) — The researcher used [EasyEdit](../../Software/Tools/AML.S0006%20-%20EasyEdit.md) with the MEND editing method to target a factual association in Llama-2-7b, specifying Sydney instead of Canberra as the desired answer to a question about Australia's capital. [ref-5stars217](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#unexpected-benefits---organization-confusion)
- [AML.S0007 - huggingface-cli](../../Software/Tools/AML.S0007%20-%20huggingface-cli.md) — The researcher used [huggingface-cli](../../Software/Tools/AML.S0007%20-%20huggingface-cli.md) to upload model artifacts containing embedded malicious code to Hugging Face repositories, making them available for users and machine learning pipelines to retrieve and execute. [ref-5stars217](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#unexpected-benefits---organization-confusion)
- [AML.S0010 - Sliver](../../Software/Tools/AML.S0010%20-%20Sliver.md) — The researcher used code embedded in TensorFlow/Keras models to download and launch [Sliver](../../Software/Tools/AML.S0010%20-%20Sliver.md) implants during model training and inference. The implants established remote control sessions while the models continued operating. The researcher named the implant process training.bin to resemble machine learning activity. [ref-5stars217](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#unexpected-benefits---organization-confusion)

## References

- [Model Confusion - Weaponizing ML models for red teams and bounty hunters](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#unexpected-benefits---organization-confusion)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0027)
