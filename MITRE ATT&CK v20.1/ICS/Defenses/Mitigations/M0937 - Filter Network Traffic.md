# M0937 - Filter Network Traffic

[ICS](../../README.md) / [Mitigations](README.md)

Use network appliances to filter ingress or egress traffic and perform protocol-based filtering. Configure software on endpoints to filter network traffic.   Perform inline allow/denylisting of network messages based on the application layer (OSI Layer 7) protocol, especially for automation protocols. Application allowlists are beneficial when there are well-defined communication sequences, types, rates, or patterns needed during expected system operations. Application denylists may be needed if all acceptable communication sequences cannot be defined, but instead a set of known malicious uses can be denied (e.g., excessive communication  attempts, shutdown messages, invalid commands).  Devices performing these functions are often referred to as deep-packet inspection (DPI) firewalls, context-aware firewalls, or firewalls blocking specific automation/SCADA protocol aware firewalls. (Citation: Centre for the Protection of National Infrastructure February 2005)

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M0937)

## Mitigated techniques

- [T0800 - Activate Firmware Update Mode](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0800%20-%20Activate%20Firmware%20Update%20Mode/README.md)
- [T0806 - Brute Force I/O](../../Tactics/11%20TA0106%20-%20Impair%20Process%20Control/T0806%20-%20Brute%20Force%20I%20-%20O/README.md)
- [T1692.001 - Command Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/T1692.001%20-%20Command%20Message/README.md)
- [T0884 - Connection Proxy](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0884%20-%20Connection%20Proxy/README.md)
- [T0868 - Detect Operating Mode](../../Tactics/08%20TA0100%20-%20Collection/T0868%20-%20Detect%20Operating%20Mode/README.md)
- [T0816 - Device Restart/Shutdown](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T0869.001 - DNS](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0869%20-%20Standard%20Application%20Layer%20Protocol/T0869.001%20-%20DNS/README.md)
- [T0843.001 - Download All](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.001%20-%20Download%20All/README.md)
- [T1693 - Modify Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/README.md)
- [T1693.002 - Module Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.002%20-%20Module%20Firmware/README.md)
- [T0843.002 - Online Edit](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.002%20-%20Online%20Edit/README.md)
- [T0861 - Point & Tag Identification](../../Tactics/08%20TA0100%20-%20Collection/T0861%20-%20Point%20%26%20Tag%20Identification/README.md)
- [T0843.003 - Program Append](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.003%20-%20Program%20Append/README.md)
- [T0843 - Program Download](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/README.md)
- [T0845 - Program Upload](../../Tactics/08%20TA0100%20-%20Collection/T0845%20-%20Program%20Upload/README.md)
- [T0869.002 - Publish/Subscribe Protocols](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0869%20-%20Standard%20Application%20Layer%20Protocol/T0869.002%20-%20Publish%20-%20Subscribe%20Protocols/README.md)
- [T0886 - Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0886%20-%20Remote%20Services/README.md)
- [T1692.002 - Reporting Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/T1692.002%20-%20Reporting%20Message/README.md)
- [T0848 - Rogue Master](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0848%20-%20Rogue%20Master/README.md)
- [T1693.001 - System Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.001%20-%20System%20Firmware/README.md)
- [T1692 - Unauthorized Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/README.md)
- [T0859 - Valid Accounts](../../Tactics/03%20TA0110%20-%20Persistence/T0859%20-%20Valid%20Accounts/README.md)

## Sources

- [Centre for the Protection of National Infrastructure February 2005](https://www.energy.gov/sites/prod/files/Good%20Practices%20Guide%20for%20Firewall%20Deployment.pdf)
