# TA0100 - Collection

[ICS](../../README.md) / [Tactics](../README.md)

The adversary is trying to gather data of interest and domain knowledge on your ICS environment to inform their goal.

Collection consists of techniques adversaries use to gather domain knowledge and obtain contextual feedback in an ICS environment. This tactic is often performed as part of [Discovery](https://attack.mitre.org/tactics/TA0102), to compile data on control systems and targets of interest that may be used to follow through on the adversary’s objective. Examples of these techniques include observing operation states, capturing screenshots, identifying unique device roles, and gathering system and diagram schematics. Collection of this data can play a key role in planning, executing, and even revising an ICS-targeted attack. Methods of collection depend on the categories of data being targeted, which can include protocol specific, device specific, and process specific configurations and functionality. Information collected may pertain to a combination of system, supervisory, device, and network related data, which conceptually fall under high, medium, and low levels of plan operations. For example, information repositories on plant data at a high level or device specific programs at a low level. Sensitive floor plans, vendor device manuals, and other references may also be at risk and exposed on the internet or otherwise publicly accessible.

[MITRE ATT&CK record](https://attack.mitre.org/tactics/TA0100)

## Techniques

- [T0830 - Adversary-in-the-Middle](T0830%20-%20Adversary-in-the-Middle/README.md)
- [T0802 - Automated Collection](T0802%20-%20Automated%20Collection/README.md)
- [T0811 - Data from Information Repositories](T0811%20-%20Data%20from%20Information%20Repositories/README.md)
- [T0893 - Data from Local System](T0893%20-%20Data%20from%20Local%20System/README.md)
- [T0868 - Detect Operating Mode](T0868%20-%20Detect%20Operating%20Mode/README.md)
- [T0877 - I/O Image](T0877%20-%20I%20-%20O%20Image/README.md)
- [T0801 - Monitor Process State](T0801%20-%20Monitor%20Process%20State/README.md)
- [T0861 - Point & Tag Identification](T0861%20-%20Point%20%26%20Tag%20Identification/README.md)
- [T0845 - Program Upload](T0845%20-%20Program%20Upload/README.md)
- [T0852 - Screen Capture](T0852%20-%20Screen%20Capture/README.md)
- [T0887 - Wireless Sniffing](T0887%20-%20Wireless%20Sniffing/README.md)
