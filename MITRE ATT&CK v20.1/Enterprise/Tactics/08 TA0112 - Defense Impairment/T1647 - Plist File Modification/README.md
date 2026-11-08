# T1647 - Plist File Modification

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may modify property list files (plist files) to enable other malicious activity, while also potentially evading and bypassing system defenses. macOS applications use plist files, such as the <code>info.plist</code> file, to store properties and configuration settings that inform the operating system how to handle the application at runtime. Plist files are structured metadata in key-value pairs formatted in XML based on Apple's Core Foundation DTD. Plist files can be saved in text or binary format.(Citation: fileinfo plist file description) 

Adversaries can modify key-value pairs in plist files to influence system behaviors, such as hiding the execution of an application (i.e. [Hidden Window](https://attack.mitre.org/techniques/T1564/003)) or running additional commands for persistence (ex: [Launch Agent](https://attack.mitre.org/techniques/T1543/001)/[Launch Daemon](https://attack.mitre.org/techniques/T1543/004) or [Re-opened Applications](https://attack.mitre.org/techniques/T1547/007)).

For example, adversaries can add a malicious application path to the `~/Library/Preferences/com.apple.dock.plist` file, which controls apps that appear in the Dock. Adversaries can also modify the <code>LSUIElement</code> key in an application’s <code>info.plist</code> file  to run the app in the background. Adversaries can also insert key-value pairs to insert environment variables, such as <code>LSEnvironment</code>, to enable persistence via [Dynamic Linker Hijacking](https://attack.mitre.org/techniques/T1574/006).(Citation: wardle chp2 persistence)(Citation: eset_osx_flashback)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1647)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [macOS](../../../Platforms/macOS.md)

## Procedure examples

- [S1153 - Cuckoo Stealer](../../../Threat%20Intelligence/Software/Malware/S1153%20-%20Cuckoo%20Stealer.md) — [Cuckoo Stealer](https://attack.mitre.org/software/S1153) can create and populate property list (plist) files to enable execution.(Citation: Kandji Cuckoo April 2024)(Citation: SentinelOne Cuckoo Stealer May 2024) [Kandji Cuckoo April 2024](https://www.kandji.io/blog/malware-cuckoo-infostealer-spyware) · [SentinelOne Cuckoo Stealer May 2024](https://www.sentinelone.com/blog/macos-cuckoo-stealer-ensuring-detection-and-defense-as-new-samples-rapidly-emerge/)
- [S0658 - XCSSET](../../../Threat%20Intelligence/Software/Malware/S0658%20-%20XCSSET.md) — In older versions, [XCSSET](https://attack.mitre.org/software/S0658) uses the <code>plutil</code> command to modify the <code>LSUIElement</code>, <code>DFBundleDisplayName</code>, and <code>CFBundleIdentifier</code> keys in the <code>/Contents/Info.plist</code> file to change how [XCSSET](https://attack.mitre.org/software/S0658) is visible on the system. In later versions, [XCSSET](https://attack.mitre.org/software/S0658) leverages a third-party notarized `dockutil` tool to modify the `.plist` file responsible for presenting applications to the user in the Dock and LaunchPad to point to a malicious application.(Citation: trendmicro xcsset xcode project 2020)(Citation: Microsoft March 2025 XCSSET) [trendmicro xcsset xcode project 2020](https://documents.trendmicro.com/assets/pdf/XCSSET_Technical_Brief.pdf) · [Microsoft March 2025 XCSSET](https://www.microsoft.com/en-us/security/blog/2025/03/11/new-xcsset-malware-adds-new-obfuscation-persistence-techniques-to-infect-xcode-projects/)

## Mitigations

- [M1013 - Application Developer Guidance](../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Ensure applications are using Apple's developer guidance which enables hardened runtime.(Citation: Apple Developer Doco Hardened Runtime) [Apple Developer Doco Hardened Runtime](https://developer.apple.com/documentation/security/hardened_runtime)

## Detection strategies

- [DET0109 - Detection Strategy for Plist File Modification (T1647)](../../../Defenses/Detection%20Strategies/DET0109%20-%20Detection%20Strategy%20for%20Plist%20File%20Modification%20%28T1647%29.md)

## Sources

- [eset_osx_flashback](https://www.welivesecurity.com/wp-content/uploads/200x/white-papers/osx_flashback.pdf)
- [fileinfo plist file description](https://fileinfo.com/extension/plist)
- [wardle chp2 persistence](https://taomm.org/PDFs/vol1/CH%200x02%20Persistence.pdf)
