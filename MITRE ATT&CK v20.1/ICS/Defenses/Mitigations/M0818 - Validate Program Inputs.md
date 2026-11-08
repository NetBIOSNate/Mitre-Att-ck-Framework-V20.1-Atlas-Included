# M0818 - Validate Program Inputs

[ICS](../../README.md) / [Mitigations](README.md)

Devices and programs designed to interact with control system parameters should validate the format and content of all user inputs and actions to ensure the values are within intended operational ranges. These values should be evaluated and further enforced through the program logic running on the field controller. If a problematic or invalid input is identified, the programs should either utilize a predetermined safe value or enter a known safe state, while also logging or alerting on the event.(Citation: PLCTop20 Mar 2023)

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M0818)

## Mitigated techniques

- [T1692.001 - Command Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/T1692.001%20-%20Command%20Message/README.md)
- [T0836 - Modify Parameter](../../Tactics/11%20TA0106%20-%20Impair%20Process%20Control/T0836%20-%20Modify%20Parameter/README.md)

## Sources

- [PLCTop20 Mar 2023](https://plc-security.com/content/Top_20_Secure_PLC_Coding_Practices_V1.0.pdf)
