# S1071 - Rubeus

[Enterprise](../../../README.md) / [Tools](README.md)

[Rubeus](https://attack.mitre.org/software/S1071) is a C# toolset designed for raw Kerberos interaction that has been used since at least 2020, including in ransomware operations.(Citation: GitHub Rubeus March 2023)(Citation: FireEye KEGTAP SINGLEMALT October 2020)(Citation: DFIR Ryuk's Return October 2020)(Citation: DFIR Ryuk 2 Hour Speed Run November 2020)

[MITRE ATT&CK record](https://attack.mitre.org/software/S1071)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1558.004 - AS-REP Roasting](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.004%20-%20AS-REP%20Roasting/README.md)
- [T1482 - Domain Trust Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1558.001 - Golden Ticket](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.001%20-%20Golden%20Ticket/README.md)
- [T1558.003 - Kerberoasting](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.003%20-%20Kerberoasting/README.md)
- [T1558.002 - Silver Ticket](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.002%20-%20Silver%20Ticket/README.md)

## Used by

- [C0063 - 2025 Poland Wiper Attacks](../../Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md)
- [C0060 - Operation AkaiRyū](../../Campaigns/C0060%20-%20Operation%20AkaiRy%C5%AB.md)
- [G0102 - Wizard Spider](../../Groups/G0102%20-%20Wizard%20Spider.md)

## Sources

- [GitHub Rubeus March 2023](https://github.com/GhostPack/Rubeus)
- [FireEye KEGTAP SINGLEMALT October 2020](https://www.fireeye.com/blog/threat-research/2020/10/kegtap-and-singlemalt-with-a-ransomware-chaser.html)
- [DFIR Ryuk 2 Hour Speed Run November 2020](https://thedfirreport.com/2020/11/05/ryuk-speed-run-2-hours-to-ransom/)
- [DFIR Ryuk's Return October 2020](https://thedfirreport.com/2020/10/08/ryuks-return/)
