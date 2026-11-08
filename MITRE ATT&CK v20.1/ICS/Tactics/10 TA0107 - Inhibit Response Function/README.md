# TA0107 - Inhibit Response Function

[ICS](../../README.md) / [Tactics](../README.md)

The adversary is trying to prevent your safety, protection, quality assurance, and operator intervention functions from responding to a failure, hazard, or unsafe state.

Inhibit Response Function consists of techniques that adversaries use to hinder the safeguards put in place for processes and products. This may involve the inhibition of safety, protection, quality assurance, or operator intervention functions to disrupt safeguards that aim to prevent the loss of life, destruction of equipment, and disruption of production. These techniques aim to actively deter and prevent expected alarms and responses that arise due to statuses in the ICS environment. Adversaries may modify or update system logic, or even outright prevent responses with a denial-of-service. They may result in the prevention, destruction, manipulation, or modification of programs, logic, devices, and communications. As prevention functions are generally dormant, reporting and processing functions can appear fine, but may have been altered to prevent failure responses in dangerous scenarios. Unlike [Evasion](https://attack.mitre.org/tactics/TA0103), Inhibit Response Function techniques may be more intrusive, such as actively preventing responses to a known dangerous scenario. Adversaries may use these techniques to follow through with or provide cover for [Impact](https://attack.mitre.org/tactics/TA0105) techniques.

[MITRE ATT&CK record](https://attack.mitre.org/tactics/TA0107)

## Techniques

- [T0800 - Activate Firmware Update Mode](T0800%20-%20Activate%20Firmware%20Update%20Mode/README.md)
- [T0878 - Alarm Suppression](T0878%20-%20Alarm%20Suppression/README.md)
- [T1695 - Block Communications](T1695%20-%20Block%20Communications/README.md)
- [T1691 - Block Operational Technology Message](T1691%20-%20Block%20Operational%20Technology%20Message/README.md)
- [T0892 - Change Credential](T0892%20-%20Change%20Credential/README.md)
- [T0809 - Data Destruction](T0809%20-%20Data%20Destruction/README.md)
- [T0814 - Denial of Service](T0814%20-%20Denial%20of%20Service/README.md)
- [T0816 - Device Restart/Shutdown](T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T0835 - Manipulate I/O Image](T0835%20-%20Manipulate%20I%20-%20O%20Image/README.md)
- [T0838 - Modify Alarm Settings](T0838%20-%20Modify%20Alarm%20Settings/README.md)
- [T1693 - Modify Firmware](T1693%20-%20Modify%20Firmware/README.md)
- [T0851 - Rootkit](T0851%20-%20Rootkit/README.md)
- [T0881 - Service Stop](T0881%20-%20Service%20Stop/README.md)
