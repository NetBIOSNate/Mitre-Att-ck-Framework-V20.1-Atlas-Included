# T1070.005 - Network Share Connection Removal

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1070 - Indicator Removal](../README.md)

Adversaries may remove share connections that are no longer useful in order to clean up traces of their operation. Windows shared drive and [SMB/Windows Admin Shares](https://attack.mitre.org/techniques/T1021/002) connections can be removed when no longer needed. [Net](https://attack.mitre.org/software/S0039) is an example utility that can be used to remove network share connections with the <code>net use \\system\share /delete</code> command.(Citation: Technet Net Use)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1070/005)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S1159 - DUSTTRAP](../../../../Threat%20Intelligence/Software/Malware/S1159%20-%20DUSTTRAP.md) — [DUSTTRAP](https://attack.mitre.org/software/S1159) can remove network shares from infected systems.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
- [S0260 - InvisiMole](../../../../Threat%20Intelligence/Software/Malware/S0260%20-%20InvisiMole.md) — [InvisiMole](https://attack.mitre.org/software/S0260) can disconnect previously connected remote drives.(Citation: ESET InvisiMole June 2018) [ESET InvisiMole June 2018](https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/)
- [S0039 - Net](../../../../Threat%20Intelligence/Software/Tools/S0039%20-%20Net.md) — The <code>net use \\system\share /delete</code> command can be used in [Net](https://attack.mitre.org/software/S0039) to remove an established connection to a network share.(Citation: Technet Net Use) [Technet Net Use](https://technet.microsoft.com/bb490717.aspx)
- [S0400 - RobbinHood](../../../../Threat%20Intelligence/Software/Malware/S0400%20-%20RobbinHood.md) — [RobbinHood](https://attack.mitre.org/software/S0400) disconnects all network shares from the computer with the command <code>net use * /DELETE /Y</code>.(Citation: CarbonBlack RobbinHood May 2019) [CarbonBlack RobbinHood May 2019](https://www.carbonblack.com/2019/05/17/cb-tau-threat-intelligence-notification-robbinhood-ransomware-stops-181-windows-services-before-encryption/)
- [G0027 - Threat Group-3390](../../../../Threat%20Intelligence/Groups/G0027%20-%20Threat%20Group-3390.md) — [Threat Group-3390](https://attack.mitre.org/groups/G0027) has detached network shares after exfiltrating files, likely to evade detection.(Citation: SecureWorks BRONZE UNION June 2017) [SecureWorks BRONZE UNION June 2017](https://www.secureworks.com/research/bronze-union)

## Detection strategies

- [DET0103 - Behavioral Detection of Network Share Connection Removal via CLI and SMB Disconnects](../../../../Defenses/Detection%20Strategies/DET0103%20-%20Behavioral%20Detection%20of%20Network%20Share%20Connection%20Removal%20via%20CLI%20and%20SMB%20Disconnects.md)

## Sources

- [Technet Net Use](https://technet.microsoft.com/bb490717.aspx)
