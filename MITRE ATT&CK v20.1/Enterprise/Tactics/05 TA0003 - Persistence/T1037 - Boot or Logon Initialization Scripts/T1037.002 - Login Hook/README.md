# T1037.002 - Login Hook

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1037 - Boot or Logon Initialization Scripts](../README.md)

Adversaries may use a Login Hook to establish persistence executed upon user logon. A login hook is a plist file that points to a specific script to execute with root privileges upon user logon. The plist file is located in the <code>/Library/Preferences/com.apple.loginwindow.plist</code> file and can be modified using the <code>defaults</code> command-line utility. This behavior is the same for logout hooks where a script can be executed upon user logout. All hooks require administrator permissions to modify or create hooks.(Citation: Login Scripts Apple Dev)(Citation: LoginWindowScripts Apple Dev) 

Adversaries can add or insert a path to a malicious script in the <code>com.apple.loginwindow.plist</code> file, using the <code>LoginHook</code> or <code>LogoutHook</code> key-value pair. The malicious script is executed upon the next user login. If a login hook already exists, adversaries can add additional commands to an existing login hook. There can be only one login and logout hook on a system at a time.(Citation: S1 macOs Persistence)(Citation: Wardle Persistence Chapter)

**Note:** Login hooks were deprecated in 10.11 version of macOS in favor of [Launch Daemon](https://attack.mitre.org/techniques/T1543/004) and [Launch Agent](https://attack.mitre.org/techniques/T1543/001).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1037/002)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0244 - Detection Strategy for Login Hook Persistence on macOS](../../../../Defenses/Detection%20Strategies/DET0244%20-%20Detection%20Strategy%20for%20Login%20Hook%20Persistence%20on%20macOS.md)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict write access to logon scripts to specific administrators.

## Sources

- [Login Scripts Apple Dev](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CustomLogin.html)
- [LoginWindowScripts Apple Dev](https://developer.apple.com/documentation/devicemanagement/loginwindowscripts)
- [Wardle Persistence Chapter](https://taomm.org/PDFs/vol1/CH%200x02%20Persistence.pdf)
- [S1 macOs Persistence](https://www.sentinelone.com/blog/how-malware-persists-on-macos/)
