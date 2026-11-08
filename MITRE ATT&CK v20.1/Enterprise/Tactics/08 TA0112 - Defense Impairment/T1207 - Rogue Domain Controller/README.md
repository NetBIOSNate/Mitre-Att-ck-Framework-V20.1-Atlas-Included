# T1207 - Rogue Domain Controller

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may register a rogue Domain Controller to enable manipulation of Active Directory data. DCShadow may be used to create a rogue Domain Controller (DC). DCShadow is a method of manipulating Active Directory (AD) data, including objects and schemas, by registering (or reusing an inactive registration) and simulating the behavior of a DC.(Citation: DCShadow Blog) Once registered, a rogue DC may be able to inject and replicate changes into AD infrastructure for any domain object, including credentials and keys.

Registering a rogue DC involves creating a new server and nTDSDSA objects in the Configuration partition of the AD schema, which requires Administrator privileges (either Domain or local to the DC) or the KRBTGT hash.(Citation: Adsecurity Mimikatz Guide)

This technique may bypass system logging and security monitors such as security information and event management (SIEM) products (since actions taken on a rogue DC may not be reported to these sensors).(Citation: DCShadow Blog) The technique may also be used to alter and delete replication and other associated metadata to obstruct forensic analysis. Adversaries may also utilize this technique to perform [SID-History Injection](https://attack.mitre.org/techniques/T1134/005) and/or manipulate AD objects (such as accounts, access control lists, schemas) to establish backdoors for Persistence.(Citation: DCShadow Blog)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1207)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S0002 - Mimikatz](../../../Threat%20Intelligence/Software/Tools/S0002%20-%20Mimikatz.md) — [Mimikatz](https://attack.mitre.org/software/S0002)’s <code>LSADUMP::DCShadow</code> module can be used to make AD updates by temporarily setting a computer to be a DC.(Citation: Deply Mimikatz)(Citation: Adsecurity Mimikatz Guide) [Deply Mimikatz](https://github.com/gentilkiwi/mimikatz) · [Adsecurity Mimikatz Guide](https://adsecurity.org/?page_id=1821)

## Detection strategies

- [DET0276 - Detection Strategy for Rogue Domain Controller (DCShadow) Registration and Replication Abuse](../../../Defenses/Detection%20Strategies/DET0276%20-%20Detection%20Strategy%20for%20Rogue%20Domain%20Controller%20%28DCShadow%29%20Registration%20and%20Replicatio.md)

## Sources

- [DCShadow Blog](https://www.dcshadow.com/)
- [Adsecurity Mimikatz Guide](https://adsecurity.org/?page_id=1821)
