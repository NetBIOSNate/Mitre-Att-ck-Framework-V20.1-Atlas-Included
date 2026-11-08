# T1547.015 - Login Items

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may add login items to execute upon user login to gain persistence or escalate privileges. Login items are applications, documents, folders, or server connections that are automatically launched when a user logs in.(Citation: Open Login Items Apple) Login items can be added via a shared file list or Service Management Framework.(Citation: Adding Login Items) Shared file list login items can be set using scripting languages such as [AppleScript](https://attack.mitre.org/techniques/T1059/002), whereas the Service Management Framework uses the API call <code>SMLoginItemSetEnabled</code>.

Login items installed using the Service Management Framework leverage <code>launchd</code>, are not visible in the System Preferences, and can only be removed by the application that created them.(Citation: Adding Login Items)(Citation: SMLoginItemSetEnabled Schroeder 2013) Login items created using a shared file list are visible in System Preferences, can hide the application when it launches, and are executed through LaunchServices, not launchd, to open applications, documents, or URLs without using Finder.(Citation: Launch Services Apple Developer) Users and applications use login items to configure their user environment to launch commonly used services or applications, such as email, chat, and music applications.

Adversaries can utilize [AppleScript](https://attack.mitre.org/techniques/T1059/002) and [Native API](https://attack.mitre.org/techniques/T1106) calls to create a login item to spawn malicious executables.(Citation: ELC Running at startup) Prior to version 10.5 on macOS, adversaries can add login items by using [AppleScript](https://attack.mitre.org/techniques/T1059/002) to send an Apple event to the “System Events” process, which has an AppleScript dictionary for manipulating login items.(Citation: Login Items AE) Adversaries can use a command such as <code>tell application “System Events” to make login item at end with properties /path/to/executable</code>.(Citation: Startup Items Eclectic)(Citation: hexed osx.dok analysis 2019)(Citation: Add List Remove Login Items Apple Script) This command adds the path of the malicious executable to the login item file list located in <code>~/Library/Application Support/com.apple.backgroundtaskmanagementagent/backgrounditems.btm</code>.(Citation: Startup Items Eclectic) Adversaries can also use login items to launch executables that can be used to control the victim system remotely or as a means to gain privilege escalation by prompting for user credentials.(Citation: objsee mac malware 2017)(Citation: CheckPoint Dok)(Citation: objsee netwire backdoor 2019)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/015)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0281 - Dok](../../../../Threat%20Intelligence/Software/Malware/S0281%20-%20Dok.md) — [Dok](https://attack.mitre.org/software/S0281) uses AppleScript to install a login Item by sending Apple events to the <code>System Events</code> process.(Citation: hexed osx.dok analysis 2019) [hexed osx.dok analysis 2019](https://web.archive.org/web/20221007144948/http://www.hexed.in/2019/07/osxdok-analysis.html)
- [S0690 - Green Lambert](../../../../Threat%20Intelligence/Software/Malware/S0690%20-%20Green%20Lambert.md) — [Green Lambert](https://attack.mitre.org/software/S0690) can add [Login Items](https://attack.mitre.org/techniques/T1547/015) to establish persistence.(Citation: Objective See Green Lambert for OSX Oct 2021)(Citation: Glitch-Cat Green Lambert ATTCK Oct 2021) [Objective See Green Lambert for OSX Oct 2021](https://objective-see.com/blog/blog_0x68.html) · [Glitch-Cat Green Lambert ATTCK Oct 2021](https://web.archive.org/web/20211018145402/https://www.glitch-cat.com/blog/green-lambert-and-attack)
- [S0198 - NETWIRE](../../../../Threat%20Intelligence/Software/Malware/S0198%20-%20NETWIRE.md) — [NETWIRE](https://attack.mitre.org/software/S0198) can persist via startup options for Login items.(Citation: Red Canary NETWIRE January 2020) [Red Canary NETWIRE January 2020](https://redcanary.com/blog/netwire-remote-access-trojan-on-linux/)

## Detection strategies

- [DET0121 - Detection Strategy for T1547.015 – Login Items on macOS](../../../../Defenses/Detection%20Strategies/DET0121%20-%20Detection%20Strategy%20for%20T1547.015%20%E2%80%93%20Login%20Items%20on%20macOS.md)

## Sources

- [Adding Login Items](https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLoginItems.html)
- [Launch Services Apple Developer](https://developer.apple.com/documentation/coreservices/launch_services)
- [Login Items AE](https://developer.apple.com/library/archive/samplecode/LoginItemsAE/Introduction/Intro.html#//apple_ref/doc/uid/DTS10003788)
- [Open Login Items Apple](https://support.apple.com/guide/mac-help/open-items-automatically-when-you-log-in-mh15189/mac)
- [hexed osx.dok analysis 2019](https://web.archive.org/web/20221007144948/http://www.hexed.in/2019/07/osxdok-analysis.html)
- [ELC Running at startup](https://eclecticlight.co/2018/05/22/running-at-startup-when-to-use-a-login-item-or-a-launchagent-launchdaemon/)
- [Startup Items Eclectic](https://eclecticlight.co/2021/09/16/how-to-run-an-app-or-tool-at-startup/)
- [Add List Remove Login Items Apple Script](https://gist.github.com/kaloprominat/6111584)
- [CheckPoint Dok](https://blog.checkpoint.com/2017/04/27/osx-malware-catching-wants-read-https-traffic/)
- [objsee netwire backdoor 2019](https://objective-see.com/blog/blog_0x44.html)
- [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html)
- [SMLoginItemSetEnabled Schroeder 2013](https://web.archive.org/web/20160216034946/https://blog.timschroeder.net/2013/04/21/smloginitemsetenabled-demystified/)
