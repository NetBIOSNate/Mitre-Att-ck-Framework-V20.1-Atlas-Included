# C0041 - FrostyGoop Incident

[ICS](../../README.md) / [Campaigns](README.md)

[FrostyGoop Incident](https://attack.mitre.org/campaigns/C0041) took place in January 2024 against a municipal district heating company in Ukraine. Following initial access via likely exploitation of external facing services, [FrostyGoop](https://attack.mitre.org/software/S1165) was used to manipulate ENCO control systems via legitimate Modbus commands to impact the delivery of heating services to Ukrainian civilians.(Citation: Dragos FROSTYGOOP 2024)(Citation: Nozomi BUSTLEBERM 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0041)

## Software used

- [S1165 - FrostyGoop](../Software/Malware/S1165%20-%20FrostyGoop.md)

## Techniques used

- [T0826 - Loss of Availability](../../Tactics/12%20TA0105%20-%20Impact/T0826%20-%20Loss%20of%20Availability/README.md)
- [T0829 - Loss of View](../../Tactics/12%20TA0105%20-%20Impact/T0829%20-%20Loss%20of%20View/README.md)
- [T0836 - Modify Parameter](../../Tactics/11%20TA0106%20-%20Impair%20Process%20Control/T0836%20-%20Modify%20Parameter/README.md)
- [T1693.001 - System Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.001%20-%20System%20Firmware/README.md)

## Sources

- [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [Nozomi BUSTLEBERM 2024](https://www.nozominetworks.com/blog/protecting-against-frostygoop-bustleberm-malware)
