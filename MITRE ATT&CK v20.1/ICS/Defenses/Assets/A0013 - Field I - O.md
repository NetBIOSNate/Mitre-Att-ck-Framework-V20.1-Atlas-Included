# A0013 - Field I/O

[ICS](../../README.md) / [Assets](README.md)

Field I/O are devices that communicate with a controller or data aggregator to either send input data or receive output data. Input data may include readings about a given environment/device state from sensors, while output data may include data sent back to actuators for them to either undertake actions or change parameter values.(Citation: Guidance - NIST SP800-82) These devices are frequently embedded devices running on lightweight embedded operating systems or RTOSes.

[MITRE ATT&CK record](https://attack.mitre.org/assets/A0013)

**Platforms**  [Embedded](../../Platforms/Embedded.md)

## Sectors

- General

## Related assets

- **Smart Sensors** (General) — *A device that procures a voltage or current output that is representative of some physical property being measured (e.g., speed, temperature, flow).* (Citation: Guidance - NIST SP800-82) Smart sensors take this functionality and add on on-device processing and network communication.
- **Variable Frequency Drive (VFD)** (General) — *A type of drive that controls the speed, but not the precise position, of a non-servo, AC motor by varying the frequency of the electricity going to that motor. VFDs are typically used for applications where speed and power are important, but precise positioning is not.* (Citation: Guidance - NIST SP800-82) VFDs can be network connected.

## Techniques targeting this asset

- [T0800 - Activate Firmware Update Mode](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0800%20-%20Activate%20Firmware%20Update%20Mode/README.md)
- [T0830 - Adversary-in-the-Middle](../../Tactics/08%20TA0100%20-%20Collection/T0830%20-%20Adversary-in-the-Middle/README.md)
- [T1695 - Block Communications](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/README.md)
- [T1691 - Block Operational Technology Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/README.md)
- [T1691.001 - Command Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/T1691.001%20-%20Command%20Message/README.md)
- [T0885 - Commonly Used Port](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0885%20-%20Commonly%20Used%20Port/README.md)
- [T0884 - Connection Proxy](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0884%20-%20Connection%20Proxy/README.md)
- [T0809 - Data Destruction](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0809%20-%20Data%20Destruction/README.md)
- [T1694.001 - Default Credentials](../../Tactics/03%20TA0110%20-%20Persistence/T1694%20-%20Insecure%20Credentials/T1694.001%20-%20Default%20Credentials/README.md)
- [T0814 - Denial of Service](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0814%20-%20Denial%20of%20Service/README.md)
- [T0816 - Device Restart/Shutdown](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T1695.002 - Ethernet](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.002%20-%20Ethernet/README.md)
- [T0871 - Execution through API](../../Tactics/02%20TA0104%20-%20Execution/T0871%20-%20Execution%20through%20API/README.md)
- [T1694.002 - Hardcoded Credentials](../../Tactics/03%20TA0110%20-%20Persistence/T1694%20-%20Insecure%20Credentials/T1694.002%20-%20Hardcoded%20Credentials/README.md)
- [T1694 - Insecure Credentials](../../Tactics/03%20TA0110%20-%20Persistence/T1694%20-%20Insecure%20Credentials/README.md)
- [T0867 - Lateral Tool Transfer](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0867%20-%20Lateral%20Tool%20Transfer/README.md)
- [T0801 - Monitor Process State](../../Tactics/08%20TA0100%20-%20Collection/T0801%20-%20Monitor%20Process%20State/README.md)
- [T0834 - Native API](../../Tactics/02%20TA0104%20-%20Execution/T0834%20-%20Native%20API/README.md)
- [T0888 - Remote System Information Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0888%20-%20Remote%20System%20Information%20Discovery/README.md)
- [T0847 - Replication Through Removable Media](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0847%20-%20Replication%20Through%20Removable%20Media/README.md)
- [T1691.002 - Reporting Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/T1691.002%20-%20Reporting%20Message/README.md)
- [T0851 - Rootkit](../../Tactics/05%20TA0103%20-%20Evasion/T0851%20-%20Rootkit/README.md)
- [T1695.001 - Serial COM](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.001%20-%20Serial%20COM/README.md)
- [T0862 - Supply Chain Compromise](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0862%20-%20Supply%20Chain%20Compromise/README.md)
- [T0859 - Valid Accounts](../../Tactics/03%20TA0110%20-%20Persistence/T0859%20-%20Valid%20Accounts/README.md)
- [T1695.003 - Wi-Fi](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.003%20-%20Wi-Fi/README.md)
- [T0860 - Wireless Compromise](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0860%20-%20Wireless%20Compromise/README.md)
- [T0887 - Wireless Sniffing](../../Tactics/06%20TA0102%20-%20Discovery/T0887%20-%20Wireless%20Sniffing/README.md)

## Sources

- [Guidance - NIST SP800-82](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf)
