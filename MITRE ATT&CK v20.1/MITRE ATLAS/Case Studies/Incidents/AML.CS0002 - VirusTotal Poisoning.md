# AML.CS0002 - VirusTotal Poisoning

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

McAfee Advanced Threat Research noticed an increase in reports of a certain ransomware family that was out of the ordinary. Case investigation revealed that many samples of that particular ransomware family were submitted through a popular virus-sharing platform within a short amount of time. Further investigation revealed that based on string similarity the samples were all equivalent, and based on code similarity they were between 98 and 74 percent similar. Interestingly enough, the compile time was the same for all the samples. After more digging, researchers discovered that someone used 'metame' a metamorphic code manipulating tool to manipulate the original file towards mutant variants. The variants would not always be executable, but are still classified as the same ransomware family.

**Type**  Incident

**Actor**  Unknown

**Target**  VirusTotal

**Reporter**  McAfee Advanced Threat Research

**Activity period**  2020

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016.000 - Adversarial AI Attack Implementations](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.000%20-%20Adversarial%20AI%20Attack%20Implementations/README.md)

The actor obtained [metame](https://github.com/a0rtega/metame), a simple metamorphic code engine for arbitrary executables.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0043 - Craft Adversarial Data](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md)

The actor used a malware sample from a prevalent ransomware family as a start to create "mutant" variants.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.002 - Data Repository](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.002%20-%20Data%20Repository/README.md)

The actor uploaded "mutant" samples to the platform.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0020 - Training Data Poisoning](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md)

Several vendors started to classify the files as the ransomware family even though most of them won't run.
The "mutant" samples poisoned the dataset the ML model(s) use to identify and classify this ransomware family.

**Next**  End of path

## Uses

- [AML.S0001 - metame](../../Software/Tools/AML.S0001%20-%20metame.md) — The actor used [metame](../../Software/Tools/AML.S0001%20-%20metame.md) to generate mutated variants of a ransomware executable.

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0002)
