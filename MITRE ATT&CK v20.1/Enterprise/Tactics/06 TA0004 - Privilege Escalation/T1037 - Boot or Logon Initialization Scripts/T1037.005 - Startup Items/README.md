# T1037.005 - Startup Items

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1037 - Boot or Logon Initialization Scripts](../README.md)

Adversaries may use startup items automatically executed at boot initialization to establish persistence. Startup items execute during the final phase of the boot process and contain shell scripts or other executable files along with configuration information used by the system to determine the execution order for all startup items.(Citation: Startup Items)

This is technically a deprecated technology (superseded by [Launch Daemon](https://attack.mitre.org/techniques/T1543/004)), and thus the appropriate folder, <code>/Library/StartupItems</code> isn’t guaranteed to exist on the system by default, but does appear to exist by default on macOS Sierra. A startup item is a directory whose executable and configuration property list (plist), <code>StartupParameters.plist</code>, reside in the top-level directory. 

An adversary can create the appropriate folders/files in the StartupItems directory to register their own persistence mechanism.(Citation: Methods of Mac Malware Persistence) Additionally, since StartupItems run during the bootup phase of macOS, they will run as the elevated root user.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1037/005)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Since StartupItems are deprecated, preventing all users from writing to the <code>/Library/StartupItems</code> directory would prevent any startup items from getting registered.

## Procedure examples

- [S0283 - jRAT](../../../../Threat%20Intelligence/Software/Malware/S0283%20-%20jRAT.md) — [jRAT](https://attack.mitre.org/software/S0283) can list and manage startup entries.(Citation: Kaspersky Adwind Feb 2016) [Kaspersky Adwind Feb 2016](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07195002/KL_AdwindPublicReport_2016.pdf)

## Detection strategies

- [DET0429 - Detect Modification of macOS Startup Items](../../../../Defenses/Detection%20Strategies/DET0429%20-%20Detect%20Modification%20of%20macOS%20Startup%20Items.md)

## Sources

- [Startup Items](https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/StartupItems.html)
- [Methods of Mac Malware Persistence](https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf)
