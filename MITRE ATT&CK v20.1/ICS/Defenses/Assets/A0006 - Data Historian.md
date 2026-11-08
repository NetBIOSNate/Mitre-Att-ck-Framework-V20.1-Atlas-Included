# A0006 - Data Historian

[ICS](../../README.md) / [Assets](README.md)

Data historians, or historian, are systems used to collect and store data, including telemetry, events, alerts, and alarms about the operational process and supporting devices. The historian typically utilizes a database to store this data, and commonly provide tools and interfaces to support the analysis of the data. Data historians are often used to support various engineering or business analysis functions and therefore commonly needs access from the corporate network. Data historians often work in a hierarchical paradigm where lower/site level historians collect and store data which is then aggregated into a site/plant level historian. Therefore, data historians often have remote services that can be accessed externally from the ICS network. Many data historian vendors have designed their software to securely transfer data between the ICS and business networks instead of requiring business systems to access the data historian in the ICS network directly.

[MITRE ATT&CK record](https://attack.mitre.org/assets/A0006)

**Platforms**  [Embedded](../../Platforms/Embedded.md), [Linux](../../Platforms/Linux.md), [Windows](../../Platforms/Windows.md)

## Sectors

- General

## Techniques targeting this asset

- [T0830 - Adversary-in-the-Middle](../../Tactics/08%20TA0100%20-%20Collection/T0830%20-%20Adversary-in-the-Middle/README.md)
- [T0878 - Alarm Suppression](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0878%20-%20Alarm%20Suppression/README.md)
- [T0802 - Automated Collection](../../Tactics/08%20TA0100%20-%20Collection/T0802%20-%20Automated%20Collection/README.md)
- [T0895 - Autorun Image](../../Tactics/02%20TA0104%20-%20Execution/T0895%20-%20Autorun%20Image/README.md)
- [T1695 - Block Communications](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/README.md)
- [T0846.002 - Broadcast Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.002%20-%20Broadcast%20Discovery/README.md)
- [T0892 - Change Credential](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0892%20-%20Change%20Credential/README.md)
- [T1701 - Command and Scripting Interpreter](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T0885 - Commonly Used Port](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0885%20-%20Commonly%20Used%20Port/README.md)
- [T0884 - Connection Proxy](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0884%20-%20Connection%20Proxy/README.md)
- [T0809 - Data Destruction](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0809%20-%20Data%20Destruction/README.md)
- [T0811 - Data from Information Repositories](../../Tactics/08%20TA0100%20-%20Collection/T0811%20-%20Data%20from%20Information%20Repositories/README.md)
- [T0893 - Data from Local System](../../Tactics/08%20TA0100%20-%20Collection/T0893%20-%20Data%20from%20Local%20System/README.md)
- [T1694.001 - Default Credentials](../../Tactics/03%20TA0110%20-%20Persistence/T1694%20-%20Insecure%20Credentials/T1694.001%20-%20Default%20Credentials/README.md)
- [T0814 - Denial of Service](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0814%20-%20Denial%20of%20Service/README.md)
- [T0816 - Device Restart/Shutdown](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T0869.001 - DNS](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0869%20-%20Standard%20Application%20Layer%20Protocol/T0869.001%20-%20DNS/README.md)
- [T1695.002 - Ethernet](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.002%20-%20Ethernet/README.md)
- [T0820 - Exploitation for Evasion](../../Tactics/05%20TA0103%20-%20Evasion/T0820%20-%20Exploitation%20for%20Evasion/README.md)
- [T0890 - Exploitation for Privilege Escalation](../../Tactics/04%20TA0111%20-%20Privilege%20Escalation/T0890%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T0866 - Exploitation of Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0866%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T0822 - External Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0822%20-%20External%20Remote%20Services/README.md)
- [T0823 - Graphical User Interface](../../Tactics/02%20TA0104%20-%20Execution/T0823%20-%20Graphical%20User%20Interface/README.md)
- [T0874 - Hooking](../../Tactics/02%20TA0104%20-%20Execution/T0874%20-%20Hooking/README.md)
- [T0872 - Indicator Removal on Host](../../Tactics/05%20TA0103%20-%20Evasion/T0872%20-%20Indicator%20Removal%20on%20Host/README.md)
- [T1694 - Insecure Credentials](../../Tactics/03%20TA0110%20-%20Persistence/T1694%20-%20Insecure%20Credentials/README.md)
- [T1701.006 - JavaScript](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.006%20-%20JavaScript/README.md)
- [T0849 - Masquerading](../../Tactics/05%20TA0103%20-%20Evasion/T0849%20-%20Masquerading/README.md)
- [T0801 - Monitor Process State](../../Tactics/08%20TA0100%20-%20Collection/T0801%20-%20Monitor%20Process%20State/README.md)
- [T0846.003 - Multicast Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.003%20-%20Multicast%20Discovery/README.md)
- [T0834 - Native API](../../Tactics/02%20TA0104%20-%20Execution/T0834%20-%20Native%20API/README.md)
- [T0840 - Network Connection Enumeration](../../Tactics/06%20TA0102%20-%20Discovery/T0840%20-%20Network%20Connection%20Enumeration/README.md)
- [T0842 - Network Sniffing](../../Tactics/06%20TA0102%20-%20Discovery/T0842%20-%20Network%20Sniffing/README.md)
- [T0861 - Point & Tag Identification](../../Tactics/08%20TA0100%20-%20Collection/T0861%20-%20Point%20%26%20Tag%20Identification/README.md)
- [T0846.001 - Port Scan](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.001%20-%20Port%20Scan/README.md)
- [T1701.001 - PowerShell](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.001%20-%20PowerShell/README.md)
- [T0869.002 - Publish/Subscribe Protocols](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0869%20-%20Standard%20Application%20Layer%20Protocol/T0869.002%20-%20Publish%20-%20Subscribe%20Protocols/README.md)
- [T1701.005 - Python](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.005%20-%20Python/README.md)
- [T0886 - Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0886%20-%20Remote%20Services/README.md)
- [T0846 - Remote System Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/README.md)
- [T0888 - Remote System Information Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0888%20-%20Remote%20System%20Information%20Discovery/README.md)
- [T0847 - Replication Through Removable Media](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0847%20-%20Replication%20Through%20Removable%20Media/README.md)
- [T0848 - Rogue Master](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0848%20-%20Rogue%20Master/README.md)
- [T0851 - Rootkit](../../Tactics/05%20TA0103%20-%20Evasion/T0851%20-%20Rootkit/README.md)
- [T0881 - Service Stop](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0881%20-%20Service%20Stop/README.md)
- [T0869 - Standard Application Layer Protocol](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0869%20-%20Standard%20Application%20Layer%20Protocol/README.md)
- [T0862 - Supply Chain Compromise](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0862%20-%20Supply%20Chain%20Compromise/README.md)
- [T0894 - System Binary Proxy Execution](../../Tactics/05%20TA0103%20-%20Evasion/T0894%20-%20System%20Binary%20Proxy%20Execution/README.md)
- [T1701.003 - Unix Shell](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.003%20-%20Unix%20Shell/README.md)
- [T0859 - Valid Accounts](../../Tactics/03%20TA0110%20-%20Persistence/T0859%20-%20Valid%20Accounts/README.md)
- [T1701.004 - Visual Basic](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.004%20-%20Visual%20Basic/README.md)
- [T1695.003 - Wi-Fi](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.003%20-%20Wi-Fi/README.md)
- [T1701.002 - Windows Command Shell](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.002%20-%20Windows%20Command%20Shell/README.md)
