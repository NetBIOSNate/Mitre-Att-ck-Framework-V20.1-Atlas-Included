# C0041 - FrostyGoop Incident

[Enterprise](../../README.md) / [Campaigns](README.md)

[FrostyGoop Incident](https://attack.mitre.org/campaigns/C0041) took place in January 2024 against a municipal district heating company in Ukraine. Following initial access via likely exploitation of external facing services, [FrostyGoop](https://attack.mitre.org/software/S1165) was used to manipulate ENCO control systems via legitimate Modbus commands to impact the delivery of heating services to Ukrainian civilians.(Citation: Dragos FROSTYGOOP 2024)(Citation: Nozomi BUSTLEBERM 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0041)

## Techniques used

- [T1071 - Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/README.md)
- [T1689 - Downgrade Attack](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1689%20-%20Downgrade%20Attack/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1003.002 - Security Account Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)

## Sources

- [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [Nozomi BUSTLEBERM 2024](https://www.nozominetworks.com/blog/protecting-against-frostygoop-bustleberm-malware)
