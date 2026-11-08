# T1127.003 - JamPlus

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1127 - Trusted Developer Utilities Proxy Execution](../README.md)

Adversaries may use `JamPlus` to proxy the execution of a malicious script. `JamPlus` is a build utility tool for code and data build systems. It works with several popular compilers and can be used for generating workspaces in code editors such as Visual Studio.(Citation: JamPlus manual)

Adversaries may abuse the `JamPlus` build utility to execute malicious scripts via a `.jam` file, which describes the build process and required dependencies. Because the malicious script is executed from a reputable developer tool, it may subvert application control security systems such as Smart App Control.(Citation: Cyble)(Citation: Elastic Security Labs)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1127/003)

**Tactics**  [Execution](../../../04%20TA0002%20-%20Execution/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — JamPlus may not be necessary within a given environment and should be removed if not used.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Consider blocking or restricting JamPlus if not required.

## Detection strategies

- [DET0585 - Behavior-chain detection strategy for T1127.003 Trusted Developer Utilities Proxy Execution: JamPlus (Windows)](../../../../Defenses/Detection%20Strategies/DET0585%20-%20Behavior-chain%20detection%20strategy%20for%20T1127.003%20Trusted%20Developer%20Utilities%20Proxy%20Exe.md)

## Sources

- [Cyble](https://cyble.com/blog/reputation-hijacking-with-jamplus-a-maneuver-to-bypass-smart-app-control-sac/)
- [Elastic Security Labs](https://www.elastic.co/security-labs/dismantling-smart-app-control)
- [JamPlus manual](https://jamplus.github.io/jamplus/quick_start.html)
