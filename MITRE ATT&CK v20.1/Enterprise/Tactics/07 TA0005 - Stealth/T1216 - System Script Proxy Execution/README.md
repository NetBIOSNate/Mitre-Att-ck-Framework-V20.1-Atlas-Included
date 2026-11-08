# T1216 - System Script Proxy Execution

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may use trusted scripts, often signed with certificates, to proxy the execution of malicious files. Several Microsoft signed scripts that have been downloaded from Microsoft or are default on Windows installations can be used to proxy execution of other files.(Citation: LOLBAS Project) This behavior may be abused by adversaries to execute malicious files that could bypass application control and signature validation on systems.(Citation: GitHub Ultimate AppLocker Bypass List)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1216)

**Tactics**  [Stealth](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1216.001 - PubPrn](T1216.001%20-%20PubPrn/README.md)
- [T1216.002 - SyncAppvPublishingServer](T1216.002%20-%20SyncAppvPublishingServer/README.md)

## Mitigations

- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Certain signed scripts that can be used to execute other programs may not be necessary within a given environment. Use application control configured to block execution of these scripts if they are not required for a given system or network to prevent potential misuse by adversaries.

## Detection strategies

- [DET0466 - Detection of Script-Based Proxy Execution via Signed Microsoft Utilities](../../../Defenses/Detection%20Strategies/DET0466%20-%20Detection%20of%20Script-Based%20Proxy%20Execution%20via%20Signed%20Microsoft%20Utilities.md)

## Sources

- [GitHub Ultimate AppLocker Bypass List](https://github.com/api0cradle/UltimateAppLockerByPassList)
- [LOLBAS Project](https://github.com/LOLBAS-Project/LOLBAS#criteria)
