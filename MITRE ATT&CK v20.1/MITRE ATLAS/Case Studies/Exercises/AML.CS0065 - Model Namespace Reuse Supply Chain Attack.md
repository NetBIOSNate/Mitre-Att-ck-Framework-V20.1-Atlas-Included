# AML.CS0065 - Model Namespace Reuse Supply Chain Attack

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Unit 42 researchers demonstrated an AI supply chain attack in which an attacker reclaims a deleted Hugging Face author namespace and publishes a malicious model under the same historical Author/ModelName identifier. Applications and model catalogs that retain unpinned references to that identifier may resolve and deploy the adversary-controlled replacement rather than the originally trusted artifact.

The attack can affect deleted models and models whose ownership was transferred to a new Hugging Face author. In the ownership-transfer scenario, Hugging Face redirects requests for the old path to the new model location, allowing stale references to continue working. If the original author namespace is later deleted and reclaimed by an attacker, the attacker can recreate the old path and cause it to resolve to a malicious model instead of the legitimate redirected model.

Unit 42 demonstrated this technique against Hugging Face-backed model catalogs in Google Vertex AI and Azure AI Foundry. The researchers embedded reverse-shell payloads in replacement models and obtained code execution in the deployed endpoint environments. They also identified reusable model references in open-source code repositories, documentation, default arguments, example notebooks, and downstream model registries, which could expose users who do not directly interact with Hugging Face.

**Type**  Exercise

**Target**  Users of Hugging Face-backed model catalogs, code pipelines, and cloud integrations

**Activity period**  2025-09-03

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0095 - Search Open Websites/Domains](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0095%20-%20Search%20Open%20Websites%20-%20Domains/README.md)

Unit 42 reviewed public Hugging Face-backed model catalogs, Hugging Face author pages, and open-source repositories to identify references to models whose original author namespace had been deleted and was available for registration. They identified stale references in cloud catalogs, source code, documentation, default arguments, and example notebooks.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

Unit 42 registered a Hugging Face organization using an abandoned namespace associated with a previously trusted model path. The original owner's account was not compromised.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0074 - Masquerading](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0074%20-%20Masquerading/README.md)

By recreating the namespace, Unit 42 made the malicious artifact appear to be the formerly trusted model. For transferred models, reclaiming the old namespace displaced the legacy redirect to the legitimate model's new location.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0018.002 - Embed Malware](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.002%20-%20Embed%20Malware/README.md)

Unit 42 prepared attacker-controlled model artifacts containing a payload that initiated a reverse shell when deployed or loaded.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0115.001 - Models](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.001%20-%20Models/README.md)

Unit 42 uploaded the malicious model under the reclaimed namespace using the original Author/ModelName identifier.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.003 - Model Repository](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md)

A cloud model catalog, application, or deployment pipeline resolved its stale name-only model reference to the attacker-controlled replacement model. Unit 42 demonstrated this through Vertex AI and Azure AI Foundry deployments.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.000 - Unsafe AI Artifacts](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md)

When a user or service deployed the malicious model, loading or deployment executed the embedded payload in the model endpoint environment.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0014 - Command and Control](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/README.md) / [AML.T0072 - Cyber Communication Channel](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0072%20-%20Cyber%20Communication%20Channel/README.md)

The payload established a reverse shell from the deployed endpoint to researcher-controlled infrastructure.

**Next**  End of path

## Attributed to

- [AML.E0034 - Unit 42](../../Entities/AML.E0034%20-%20Unit%2042.md) (Security Evaluation)

## References

- [Model Namespace Reuse: An AI Supply-Chain Attack Exploiting Model Name Trust](https://unit42.paloaltonetworks.com/model-namespace-reuse/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0065)
