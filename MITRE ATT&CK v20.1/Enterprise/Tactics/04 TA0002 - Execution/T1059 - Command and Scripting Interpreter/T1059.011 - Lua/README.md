# T1059.011 - Lua

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1059 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse Lua commands and scripts for execution. Lua is a cross-platform scripting and programming language primarily designed for embedded use in applications. Lua can be executed on the command-line (through the stand-alone lua interpreter), via scripts (<code>.lua</code>), or from Lua-embedded programs (through the <code>struct lua_State</code>).(Citation: Lua main page)(Citation: Lua state)

Lua scripts may be executed by adversaries for malicious purposes. Adversaries may incorporate, abuse, or replace existing Lua interpreters to allow for malicious Lua command execution at runtime.(Citation: PoetRat Lua)(Citation: Lua Proofpoint Sunseed)(Citation: Cyphort EvilBunny)(Citation: Kaspersky Lua)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1059/011)

**Tactics**  [Execution](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0396 - EvilBunny](../../../../Threat%20Intelligence/Software/Malware/S0396%20-%20EvilBunny.md) — [EvilBunny](https://attack.mitre.org/software/S0396) has used Lua scripts to execute payloads.(Citation: Cyphort EvilBunny) [Cyphort EvilBunny](https://web.archive.org/web/20150311013500/http:/www.cyphort.com/evilbunny-malware-instrumented-lua/)
- [S1188 - Line Runner](../../../../Threat%20Intelligence/Software/Malware/S1188%20-%20Line%20Runner.md) — [Line Runner](https://attack.mitre.org/software/S1188) utilizes Lua scripts for command execution.(Citation: Cisco ArcaneDoor 2024)(Citation: CCCS ArcaneDoor 2024) [CCCS ArcaneDoor 2024](https://www.cyber.gc.ca/en/news-events/cyber-activity-impacting-cisco-asa-vpns) · [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [S0428 - PoetRAT](../../../../Threat%20Intelligence/Software/Malware/S0428%20-%20PoetRAT.md) — [PoetRAT](https://attack.mitre.org/software/S0428) has executed a Lua script through a Lua interpreter for Windows.(Citation: Talos PoetRAT October 2020) [Talos PoetRAT October 2020](https://blog.talosintelligence.com/2020/10/poetrat-update.html)
- [S1240 - RedLine Stealer](../../../../Threat%20Intelligence/Software/Malware/S1240%20-%20RedLine%20Stealer.md) — [RedLine Stealer](https://attack.mitre.org/software/S1240) malware has leveraged Lua bytecode to perform malicious behavior.(Citation: McAfee RedLine Stealer April 2024) [McAfee RedLine Stealer April 2024](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/redline-stealer-a-novel-approach/)
- [S0125 - Remsec](../../../../Threat%20Intelligence/Software/Malware/S0125%20-%20Remsec.md) — [Remsec](https://attack.mitre.org/software/S0125) can use modules written in Lua for execution.(Citation: Kaspersky Lua) [Kaspersky Lua](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07190154/The-ProjectSauron-APT_research_KL.pdf)

## Detection strategies

- [DET0101 - Detection Strategy for Lua Scripting Abuse](../../../../Defenses/Detection%20Strategies/DET0101%20-%20Detection%20Strategy%20for%20Lua%20Scripting%20Abuse.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Inventory systems for unauthorized Lua installations.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Denylist Lua interpreters where appropriate.
- [M1033 - Limit Software Installation](../../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Prevent users from installing Lua where not required.

## Sources

- [Kaspersky Lua](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07190154/The-ProjectSauron-APT_research_KL.pdf)
- [Lua main page](https://www.lua.org/start.html)
- [Lua state](https://pgl.yoyo.org/luai/i/lua_State)
- [Cyphort EvilBunny](https://web.archive.org/web/20150311013500/http:/www.cyphort.com/evilbunny-malware-instrumented-lua/)
- [PoetRat Lua](https://blog.talosintelligence.com/poetrat-update/)
- [Lua Proofpoint Sunseed](https://www.proofpoint.com/us/blog/threat-insight/asylum-ambuscade-state-actor-uses-compromised-private-ukrainian-military-emails)
