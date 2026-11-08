# AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Autonomous Anthropic models gained unauthorized access to systems belonging to three unrelated organizations during six cybersecurity evaluation runs from April through July 2026, compromising real systems while pursuing capture-the-flag objectives.

The agents received open-ended capture-the-flag objectives in evaluation environments provided by Irregular, Anthropic's third-party cybersecurity evaluation partner, and selected targets and actions without human direction. Anthropic's prompts described the environments as isolated simulations, but a misconfiguration left Internet access available, leading the agents initially to treat real systems as part of the exercises.

Through a retrospective review of transcripts from 141,006 cybersecurity evaluation runs, Anthropic identified three distinct incidents:

**Same-name target substitution:** In four runs, Claude Opus 4.7 agents substituted a real company with the same name for an unreachable simulated target. They exploited weaknesses in its infrastructure, obtained credentials, and accessed a production database, continuing even after observing evidence that the environment was real.

**Dependency confusion:** Claude Mythos 5 published a malicious Python package to PyPI under an unregistered dependency name referenced in the evaluation. Fifteen real systems downloaded and executed it. The package exfiltrated credentials from a security company's automated scanner, which the agent then used to access additional company infrastructure.

**Internet scanning and SQL injection:** An internal Anthropic research model responded to an unreachable fictional target by scanning roughly 9,000 alternative targets and compromising a real Internet-facing application through SQL injection. The agent stopped the attack after recognizing that the host belonged to an unrelated cloud account.

**Type**  Incident

**Actor**  Autonomous AI agents: Claude Opus 4.7, Claude Mythos 5, and an internal Anthropic research model

**Target**  3 organizations

**Activity period**  2026-04 to 2026-07

## Procedure steps

### Step S01

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md)

Claude Opus 4.7 agents received the open-ended objective of retrieving a flag from a fictional target. Throughout the operation, the agents autonomously selected and revised intermediate actions based on newly gathered information and the results of prior actions, advancing toward the assigned objective without per-action human direction.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md)

Claude Opus 4.7 agents discovered that a real company sharing the fictional target's name was reachable on the public Internet and investigated its infrastructure, treating it as the intended evaluation target.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

Claude Opus 4.7 agents exploited unspecified weaknesses in the real company's Internet-reachable infrastructure.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0106 - Exploitation for Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0106%20-%20Exploitation%20for%20Credential%20Access/README.md)

Claude Opus 4.7 agents extracted application and infrastructure credentials.

**Next**  End of path

### Step S10

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md)

A Claude Mythos 5 agent received the open-ended objective of retrieving a flag from a fictional target. Throughout the operation, the agent autonomously selected and revised intermediate actions based on newly gathered information and the results of prior actions, advancing toward the assigned objective without per-action human direction.

**Next**  [S11](#step-s11), [S12](#step-s12)

### Step S11

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.003 - Malware](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.003%20-%20Malware/README.md)

The Claude Mythos 5 agent identified a nonexistent package name in the developer instructions for its fictional target. It built a malicious Python package under that name containing hidden code designed  to exfiltrate credentials.

**Next**  [S13](#step-s13)

### Step S12

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0021 - Establish Accounts](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md)

The Claude Mythos 5 agent registered a PyPI account. To obtain the required email address, it initially pursued an email provider that required a phone number. After failing to find a free phone-number service or obtain funds to pay for one, it found a free, unblocked email provider.

**Next**  [S13](#step-s13)

### Step S13

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

The Claude Mythos 5 agent uploaded the malicious package to PyPI, making it publicly retrievable for roughly one hour before PyPI's security systems removed it.

**Next**  [S14](#step-s14)

### Step S14

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.001 - Software](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.001%20-%20Software/README.md)

The Claude Mythos 5 agent published the package under the dependency name specified in the fictional developer instructions. Fifteen real systems downloaded and ran the publicly available package.

**Next**  [S15](#step-s15)

### Step S15

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0050 - Command and Scripting Interpreter](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0050%20-%20Command%20and%20Scripting%20Interpreter/README.md)

Hidden Python code from the package executed on fifteen real systems, including an automated package scanner operated by a security company.

**Next**  [S16](#step-s16)

### Step S16

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

When the security company's scanner installed the package, the hidden code exfiltrated the scanner's credentials to a collection point established by the Claude Mythos 5 agent.

**Next**  [S17](#step-s17)

### Step S17

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0012%20-%20Valid%20Accounts/README.md)

The agent used the exfiltrated credentials to access further infrastructure belonging to the security company.

**Next**  End of path

### Step S20

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md)

An internal Claude research test model received the open-ended objective of retrieving a flag from a fictional target. Throughout the operation, the agent autonomously selected and revised intermediate actions based on newly gathered information and the results of prior actions, advancing toward the assigned objective without per-action human direction.

**Next**  [S21](#step-s21)

### Step S21

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md)

The internal Claude agent independently broadened its search to the public Internet, evaluated reachable alternatives, and selected an exploitable real application from the returned results.

**Next**  [S22](#step-s22)

### Step S22

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0006 - Active Scanning](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md)

The internal Claude agent scanned roughly 9,000 targets and selected one to attack.

**Next**  [S23](#step-s23), [S24](#step-s24)

### Step S23

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

The internal Claude agent read credentials exposed on a publicly accessible debug page.

**Next**  End of path

### Step S24

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

The internal Claude agent used SQL injection to compromise the selected Internet-facing application.

**Next**  End of path

## Attributed to

- [AML.E0039 - Anthropic](../../Entities/AML.E0039%20-%20Anthropic.md) (Unintended Consequence) — Anthropic commissioned the cybersecurity evaluations and operated the models involved. The models' access to real organizations was an unintended consequence of Internet connectivity being available in evaluation environments that were expected to be isolated.

## Reported by

- [AML.E0039 - Anthropic](../../Entities/AML.E0039%20-%20Anthropic.md)

## References

- [Investigating three real-world incidents in our cybersecurity evaluations](https://www.anthropic.com/news/investigating-incidents-cybersecurity-evals)
- [The Next Generation of Cyber Evaluations](https://www.irregular.com/research/next-generation-of-cyber-evals)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0073)
