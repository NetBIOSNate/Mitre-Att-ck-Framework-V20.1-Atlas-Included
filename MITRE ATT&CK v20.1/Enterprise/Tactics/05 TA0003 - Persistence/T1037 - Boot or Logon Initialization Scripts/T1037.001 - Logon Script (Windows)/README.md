# T1037.001 - Logon Script (Windows)

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1037 - Boot or Logon Initialization Scripts](../README.md)

Adversaries may use Windows logon scripts automatically executed at logon initialization to establish persistence. Windows allows logon scripts to be run whenever a specific user or group of users log into a system.(Citation: TechNet Logon Scripts) This is done via adding a path to a script to the <code>HKCU\Environment\UserInitMprLogonScript</code> Registry key.(Citation: Hexacorn Logon Scripts)

Adversaries may use these scripts to maintain persistence on a single system. Depending on the access configuration of the logon scripts, either local credentials or an administrator account may be necessary.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1037/001)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1024 - Restrict Registry Permissions](../../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Ensure proper permissions are set for Registry hives to prevent users from modifying keys for logon scripts that may lead to persistence.

## Procedure examples

- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — An [APT28](https://attack.mitre.org/groups/G0007) loader Trojan adds the Registry key <code>HKCU\Environment\UserInitMprLogonScript</code> to establish persistence.(Citation: Unit 42 Playbook Dec 2017) [Unit 42 Playbook Dec 2017](https://web.archive.org/web/20230702043312/https://pan-unit42.github.io/playbook_viewer/)
- [S0438 - Attor](../../../../Threat%20Intelligence/Software/Malware/S0438%20-%20Attor.md) — [Attor](https://attack.mitre.org/software/S0438)'s dispatcher can establish persistence via adding a Registry key with a logon script <code>HKEY_CURRENT_USER\Environment "UserInitMprLogonScript" </code>.(Citation: ESET Attor Oct 2019) [ESET Attor Oct 2019](https://www.welivesecurity.com/wp-content/uploads/2019/10/ESET_Attor.pdf)
- [G0080 - Cobalt Group](../../../../Threat%20Intelligence/Groups/G0080%20-%20Cobalt%20Group.md) — [Cobalt Group](https://attack.mitre.org/groups/G0080) has added persistence by registering the file name for the next stage malware under <code>HKCU\Environment\UserInitMprLogonScript</code>.(Citation: Morphisec Cobalt Gang Oct 2018) [Morphisec Cobalt Gang Oct 2018](https://blog.morphisec.com/cobalt-gang-2.0)
- [S0044 - JHUHUGIT](../../../../Threat%20Intelligence/Software/Malware/S0044%20-%20JHUHUGIT.md) — [JHUHUGIT](https://attack.mitre.org/software/S0044) has registered a Windows shell script under the Registry key <code>HKCU\Environment\UserInitMprLogonScript</code> to establish persistence.(Citation: ESET Sednit Part 1)(Citation: Talos Seduploader Oct 2017) [ESET Sednit Part 1](http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf) · [Talos Seduploader Oct 2017](https://blog.talosintelligence.com/2017/10/cyber-conflict-decoy-document.html)
- [S0526 - KGH_SPY](../../../../Threat%20Intelligence/Software/Malware/S0526%20-%20KGH_SPY.md) — [KGH_SPY](https://attack.mitre.org/software/S0526) has the ability to set the <code>HKCU\Environment\UserInitMprLogonScript</code> Registry key to execute logon scripts.(Citation: Cybereason Kimsuky November 2020) [Cybereason Kimsuky November 2020](https://www.cybereason.com/blog/back-to-the-future-inside-the-kimsuky-kgh-spyware-suite)
- [S0251 - Zebrocy](../../../../Threat%20Intelligence/Software/Malware/S0251%20-%20Zebrocy.md) — [Zebrocy](https://attack.mitre.org/software/S0251) performs persistence with a logon script via adding to the Registry key <code>HKCU\Environment\UserInitMprLogonScript</code>.(Citation: ESET Zebrocy Nov 2018) [ESET Zebrocy Nov 2018](https://www.welivesecurity.com/2018/11/20/sednit-whats-going-zebrocy/)

## Detection strategies

- [DET0072 - Detect Logon Script Modifications and Execution](../../../../Defenses/Detection%20Strategies/DET0072%20-%20Detect%20Logon%20Script%20Modifications%20and%20Execution.md)

## Sources

- [Hexacorn Logon Scripts](http://www.hexacorn.com/blog/2014/11/14/beyond-good-ol-run-key-part-18/)
- [TechNet Logon Scripts](https://technet.microsoft.com/en-us/library/cc758918%28v=ws.10%29.aspx)
