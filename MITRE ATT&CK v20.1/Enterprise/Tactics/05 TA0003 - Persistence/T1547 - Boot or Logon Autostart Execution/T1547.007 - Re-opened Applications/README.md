# T1547.007 - Re-opened Applications

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may modify plist files to automatically run an application when a user logs in. When a user logs out or restarts via the macOS Graphical User Interface (GUI), a prompt is provided to the user with a checkbox to "Reopen windows when logging back in".(Citation: Re-Open windows on Mac) When selected, all applications currently open are added to a property list file named <code>com.apple.loginwindow.[UUID].plist</code> within the <code>~/Library/Preferences/ByHost</code> directory.(Citation: Methods of Mac Malware Persistence)(Citation: Wardle Persistence Chapter) Applications listed in this file are automatically reopened upon the user’s next logon.

Adversaries can establish [Persistence](https://attack.mitre.org/tactics/TA0003) by adding a malicious application path to the <code>com.apple.loginwindow.[UUID].plist</code> file to execute payloads when a user logs in.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/007)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — This feature can be disabled entirely with the following terminal command: <code>defaults write -g ApplePersistence -bool no</code>.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Holding the Shift key while logging in prevents apps from opening automatically.(Citation: Re-Open windows on Mac) [Re-Open windows on Mac](https://support.apple.com/en-us/HT204005)

## Detection strategies

- [DET0125 - Detect persistence via reopened application plist modification (macOS)](../../../../Defenses/Detection%20Strategies/DET0125%20-%20Detect%20persistence%20via%20reopened%20application%20plist%20modification%20%28macOS%29.md)

## Sources

- [Re-Open windows on Mac](https://support.apple.com/en-us/HT204005)
- [Methods of Mac Malware Persistence](https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf)
- [Wardle Persistence Chapter](https://taomm.org/PDFs/vol1/CH%200x02%20Persistence.pdf)
