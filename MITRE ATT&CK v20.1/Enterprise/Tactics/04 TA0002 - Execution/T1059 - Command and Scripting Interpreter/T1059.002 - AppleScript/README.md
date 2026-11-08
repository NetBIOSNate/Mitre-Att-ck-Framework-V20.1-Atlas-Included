# T1059.002 - AppleScript

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1059 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse AppleScript for execution. AppleScript is a macOS scripting language designed to control applications and parts of the OS via inter-application messages called AppleEvents.(Citation: Apple AppleScript) These AppleEvent messages can be sent independently or easily scripted with AppleScript. These events can locate open windows, send keystrokes, and interact with almost any open application locally or remotely.

Scripts can be run from the command-line via <code>osascript /path/to/script</code> or <code>osascript -e "script here"</code>. Aside from the command line, scripts can be executed in numerous ways including Mail rules, Calendar.app alarms, and Automator workflows. AppleScripts can also be executed as plain text shell scripts by adding <code>#!/usr/bin/osascript</code> to the start of the script file.(Citation: SentinelOne AppleScript)

AppleScripts do not need to call <code>osascript</code> to execute. However, they may be executed from within mach-O binaries by using the macOS [Native API](https://attack.mitre.org/techniques/T1106)s <code>NSAppleScript</code> or <code>OSAScript</code>, both of which execute code independent of the <code>/usr/bin/osascript</code> command line utility.

Adversaries may abuse AppleScript to execute various behaviors, such as interacting with an open SSH connection, moving to remote machines, and even presenting users with fake dialog boxes. These events cannot start applications remotely (they can start them locally), but they can interact with applications if they're already running remotely. On macOS 10.10 Yosemite and higher, AppleScript has the ability to execute [Native API](https://attack.mitre.org/techniques/T1106)s, which otherwise would require compilation and execution in a mach-O binary file format.(Citation: SentinelOne macOS Red Team) Since this is a scripting language, it can be used to launch more common techniques as well such as a reverse shell via [Python](https://attack.mitre.org/techniques/T1059/006).(Citation: Macro Malware Targets Macs)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1059/002)

**Tactics**  [Execution](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Require that all AppleScript be signed by a trusted developer ID before being executed - this will prevent random AppleScript code from executing.(Citation: applescript signing) This subjects AppleScript code to the same scrutiny as other .app files passing through Gatekeeper. [applescript signing](https://www.engadget.com/2013/10/23/applescript-and-automator-gain-new-features-in-os-x-mavericks/)
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control where appropriate.

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has sent Mac users.scpt files to trigger malicious downloads.(Citation: Microsoft CYBERWARCON NOV 2024) [APT38](https://attack.mitre.org/groups/G0082) has targeted macOS uses with native script stagers leading to malicious paylaods.(Citation: Microsoft Axios Compromise APR 2026) [APT38](https://attack.mitre.org/groups/G0082) has also used an AppleScript-based credential harvesting component.(Citation: Microsoft Sapphire Sleet APR 2026) [Microsoft CYBERWARCON NOV 2024](https://www.microsoft.com/en-us/security/blog/2024/11/22/microsoft-shares-latest-intelligence-on-north-korean-and-chinese-threat-actors-at-cyberwarcon/) · [Microsoft Axios Compromise APR 2026](https://www.microsoft.com/en-us/security/blog/2026/04/01/mitigating-the-axios-npm-supply-chain-compromise/) · [Microsoft Sapphire Sleet APR 2026](https://www.microsoft.com/en-us/security/blog/2026/04/16/dissecting-sapphire-sleets-macos-intrusion-from-lure-to-compromise/)
- [S0482 - Bundlore](../../../../Threat%20Intelligence/Software/Malware/S0482%20-%20Bundlore.md) — [Bundlore](https://attack.mitre.org/software/S0482) can use AppleScript to inject malicious JavaScript into a browser.(Citation: MacKeeper Bundlore Apr 2019) [MacKeeper Bundlore Apr 2019](https://mackeeper.com/blog/post/610-macos-bundlore-adware-analysis/)
- [S1153 - Cuckoo Stealer](../../../../Threat%20Intelligence/Software/Malware/S1153%20-%20Cuckoo%20Stealer.md) — [Cuckoo Stealer](https://attack.mitre.org/software/S1153) can use osascript to generate a password-stealing prompt, duplicate files and folders, and set environmental variables.(Citation: Kandji Cuckoo April 2024)(Citation: SentinelOne Cuckoo Stealer May 2024) [Kandji Cuckoo April 2024](https://www.kandji.io/blog/malware-cuckoo-infostealer-spyware) · [SentinelOne Cuckoo Stealer May 2024](https://www.sentinelone.com/blog/macos-cuckoo-stealer-ensuring-detection-and-defense-as-new-samples-rapidly-emerge/)
- [S0281 - Dok](../../../../Threat%20Intelligence/Software/Malware/S0281%20-%20Dok.md) — [Dok](https://attack.mitre.org/software/S0281) uses AppleScript to create a login item for persistence.(Citation: objsee mac malware 2017) [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html)
- [S9010 - GlassWorm](../../../../Threat%20Intelligence/Software/Malware/S9010%20-%20GlassWorm.md) — [GlassWorm](https://attack.mitre.org/software/S9010) has utilized AppleScript to include `set keychainPassword to do shell script` to execute shell command that retrieves passwords from the macOS keychain.(Citation: Koi Glassworm New Tricks December 2025) [Koi Glassworm New Tricks December 2025](https://www.koi.ai/blog/glassworm-goes-mac-fresh-infrastructure-new-tricks)
- [S1048 - macOS.OSAMiner](../../../../Threat%20Intelligence/Software/Malware/S1048%20-%20macOS.OSAMiner.md) — [macOS.OSAMiner](https://attack.mitre.org/software/S1048) has used `osascript` to call itself via the `do shell script` command in the [Launch Agent](https://attack.mitre.org/techniques/T1543/001) `.plist` file.(Citation: SentinelLabs reversing run-only applescripts 2021) [SentinelLabs reversing run-only applescripts 2021](https://www.sentinelone.com/labs/fade-dead-adventures-in-reversing-malicious-run-only-applescripts/)
- [S0595 - ThiefQuest](../../../../Threat%20Intelligence/Software/Malware/S0595%20-%20ThiefQuest.md) — [ThiefQuest](https://attack.mitre.org/software/S0595) uses [AppleScript](https://attack.mitre.org/techniques/T1059/002)'s <code>osascript -e</code> command to launch [ThiefQuest](https://attack.mitre.org/software/S0595)'s persistence via [Launch Agent](https://attack.mitre.org/techniques/T1543/001) and [Launch Daemon](https://attack.mitre.org/techniques/T1543/004). (Citation: wardle evilquest parti) [wardle evilquest parti](https://objective-see.com/blog/blog_0x59.html)

## Detection strategies

- [DET0414 - Detection of AppleScript-Based Execution on macOS](../../../../Defenses/Detection%20Strategies/DET0414%20-%20Detection%20of%20AppleScript-Based%20Execution%20on%20macOS.md)

## Sources

- [Apple AppleScript](https://developer.apple.com/library/archive/documentation/AppleScript/Conceptual/AppleScriptLangGuide/introduction/ASLR_intro.html)
- [SentinelOne macOS Red Team](https://www.sentinelone.com/blog/macos-red-team-calling-apple-apis-without-building-binaries/)
- [SentinelOne AppleScript](https://www.sentinelone.com/blog/how-offensive-actors-use-applescript-for-attacking-macos/)
- [Macro Malware Targets Macs](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/macro-malware-targets-macs/)
