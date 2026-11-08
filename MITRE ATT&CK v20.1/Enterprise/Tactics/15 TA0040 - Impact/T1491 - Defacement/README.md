# T1491 - Defacement

[Enterprise](../../../README.md) / [Impact](../README.md)

Adversaries may modify visual content available internally or externally to an enterprise network, thus affecting the integrity of the original content. Reasons for [Defacement](https://attack.mitre.org/techniques/T1491) include delivering messaging, intimidation, or claiming (possibly false) credit for an intrusion. Disturbing or offensive images may be used as a part of [Defacement](https://attack.mitre.org/techniques/T1491) in order to cause user discomfort, or to pressure compliance with accompanying messages.(Citation: Defacement Attacks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1491)

**Tactics**  [Impact](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [IaaS](../../../Platforms/IaaS.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [ESXi](../../../Platforms/ESXi.md)

## Sub-techniques

- [T1491.002 - External Defacement](T1491.002%20-%20External%20Defacement/README.md)
- [T1491.001 - Internal Defacement](T1491.001%20-%20Internal%20Defacement/README.md)

## Detection strategies

- [DET0238 - Defacement via File and Web Content Modification Across Platforms](../../../Defenses/Detection%20Strategies/DET0238%20-%20Defacement%20via%20File%20and%20Web%20Content%20Modification%20Across%20Platforms.md)

## Mitigations

- [M1053 - Data Backup](../../../Defenses/Mitigations/M1053%20-%20Data%20Backup.md) — Consider implementing IT disaster recovery plans that contain procedures for taking regular data backups that can be used to restore organizational data.(Citation: Ready.gov IT DRP) Ensure backups are stored off system and is protected from common methods adversaries may use to gain access and destroy the backups to prevent recovery. [Ready.gov IT DRP](https://www.ready.gov/business/implementation/IT)

## Sources

- [Defacement Attacks](https://www.hkcert.org/blog/defacement-attacks-understanding-and-prevention)
