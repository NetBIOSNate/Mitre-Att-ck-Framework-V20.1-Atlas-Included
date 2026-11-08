# T1037.003 - Network Logon Script

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1037 - Boot or Logon Initialization Scripts](../README.md)

Adversaries may use network logon scripts automatically executed at logon initialization to establish persistence. Network logon scripts can be assigned using Active Directory or Group Policy Objects.(Citation: Petri Logon Script AD) These logon scripts run with the privileges of the user they are assigned to. Depending on the systems within the network, initializing one of these scripts could apply to more than one or potentially all systems.  
 
Adversaries may use these scripts to maintain persistence on a network. Depending on the access configuration of the logon scripts, either local credentials or an administrator account may be necessary.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1037/003)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict write access to logon scripts to specific administrators.

## Procedure examples

- [S9051 - The Gentlemen Ransomware](../../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has utilized the domain’s NETLOGON share to distribute the malicious payload to all domain-joined systems.(Citation: TrendAI_TheGentlemen_Sept2025) [TrendAI_TheGentlemen_Sept2025](https://www.trendaisecurity.com/en-us/resources-insights/trendai-security-blog/unmasking-the-gentlemen-ransomware)

## Detection strategies

- [DET0367 - Detect Network Logon Script Abuse via Multi-Event Correlation on Windows](../../../../Defenses/Detection%20Strategies/DET0367%20-%20Detect%20Network%20Logon%20Script%20Abuse%20via%20Multi-Event%20Correlation%20on%20Windows.md)

## Sources

- [Petri Logon Script AD](https://www.petri.com/setting-up-logon-script-through-active-directory-users-computers-windows-server-2008)
