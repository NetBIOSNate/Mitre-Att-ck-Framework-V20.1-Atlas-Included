# AML.CS0049 - Supply Chain Compromise via Poisoned ClawdBot Skill

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

A security researcher demonstrated a proof-of-concept supply chain attack using a poisoned ClawdBot Skill shared on ClawdHub, a Skill registry for agents. The poisoned Skill contained a prompt injection that caused ClawdBot to execute a shell command that reached the researcher's server. Although the researcher here used this access simply to warn users about the danger, they could have instead delivered a malicious payload and compromised the user's system. The security researcher recorded 16 different users who downloaded and executed the poisoned Skill in the first 8 hours of it being published on ClawdHub.

**Type**  Exercise

**Target**  ClawdBot (now OpenClaw)

**Activity period**  2026-01-26

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017 - Develop Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/README.md)

The researcher created a simple web server to log requests.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0008.002 - Domains](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.002%20-%20Domains/README.md)

The researcher registered the domain `clawdhub-skill.com` to host their web server.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researcher crafted a prompt injection designed to cause Claude Code to execute a `curl` command to the researcher's `clawdhub-skill.com` domain.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0115.002 - AI Agent Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.002%20-%20AI%20Agent%20Tools/README.md)

The researcher developed a poisoned ClawdBot Skill called "What Would Elon Do?" The Skill contained the malicious prompt in the `rules/logic.md` file, which is read when the Skill is activated. The researcher published their Skill to ClawdHub.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0111 - AI Supply Chain Reputation Inflation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0111%20-%20AI%20Supply%20Chain%20Reputation%20Inflation/README.md)

The researcher used a script to increase the number of downloads of their Skill to increase visibility and gain trust.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.005 - AI Agent Tool](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.005%20-%20AI%20Agent%20Tool/README.md)

Users downloaded the poisoned Skill from ClawdHub.

Note that ClawdHub does not display all files that are part of the Skill, making it hard for users to review Skills before downloading them.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0110.000 - Definition and Instructions](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0110%20-%20AI%20Agent%20Tool%20Poisoning/AML.T0110.000%20-%20Definition%20and%20Instructions/README.md)

The poisoned Skill included malicious model-readable instructions in `rules/logic.md`. Once the Skill was installed and made available to the agent, these instructions altered how Claude Code handled requests associated with the Skill.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.002 - Poisoned AI Agent Tool](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.002%20-%20Poisoned%20AI%20Agent%20Tool/README.md)

When a user asked Claude Code "what would Elon do?" it calls the poisoned Skill.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

Claude Code read all files that are part of the Skill, executing the malicious prompt in the `rules/logic.md` file.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0074 - Masquerading](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0074%20-%20Masquerading/README.md)

Claude Code prompted the user before executing the shell command. The researcher had registered the `https://clawdhub-skill.com` domain, which appears to be legitimate and may be confused with the legitimate `https://clawdhub.com` domain, causing the user to select confirm.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

Claude Code executed the shell command using it's `bash` tool.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048 - External Harms](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/README.md)

In this proof of concept, the researcher simply pinged their server and warned the user of the dangers of using Skills without reading the source code, causing no harm. However, they could have delivered a malicious payload, and caused a variety of harms, including:
- Exfiltrating the user's codebase
- Injecting backdoors into the user's codebase
- Stealing the user's credentials
- Installing malware or crypto miners
- Performing anything else Claude Code is capable of

**Next**  End of path

## References

- [eating lobster souls Part II: the supply chain (aka - backdooring the #1 downloaded clawdhub skill)](https://x.com/theonejvo/status/2015892980851474595)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0049)
