# T1662 - Data Destruction

[Mobile](../../../README.md) / [Impact](../README.md)

Adversaries may destroy data and files on specific devices or in large numbers to interrupt availability to systems, services, and network resources. Data destruction is likely to render stored data irrecoverable by forensic techniques through overwriting files or data on local and remote drives.  

To achieve data destruction, adversaries may use the `pm uninstall` command to uninstall packages or the `rm` command to remove specific files. For example, adversaries may first use `pm uninstall` to uninstall non-system apps, and then use `rm (-f) <file(s)>` to delete specific files, further hiding malicious activity.(Citation: rootnik_rooting_tool)(Citation: abuse_native_linux_tools)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1662)

**Tactics**  [Impact](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Detection strategies

- [DET0671 - Detection of Data Destruction](../../../Defenses/Detection%20Strategies/DET0671%20-%20Detection%20of%20Data%20Destruction.md)

## Procedure examples

- [S1094 - BRATA](../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can perform a factory reset.(Citation: cleafy_brata_0122) [cleafy_brata_0122](https://www.cleafy.com/cleafy-labs/how-brata-is-monitoring-your-bank-account)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has deleted media files and messenger-related files on the device.(Citation: Threatfabric LightSpy 2024) Additionally, [LightSpy](https://attack.mitre.org/software/S1185) has used the AppDelete plugin to remove multiple messaging applications, such as WeChat, QQ, Telegram, Line and Whatsapp.(Citation: LinkedIn Dmitry LightSpy 2025) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [S1241 - RatMilad](../../../Threat%20Intelligence/Software/Malware/S1241%20-%20RatMilad.md) — [RatMilad](https://attack.mitre.org/software/S1241) has deleted files on the device.(Citation: ZimperiumGupta_RatMilad_Oct2022) [ZimperiumGupta_RatMilad_Oct2022](https://zimperium.com/blog/we-smell-a-ratmilad-mobile-spyware)
- [S9030 - SameCoin](../../../Threat%20Intelligence/Software/Malware/S9030%20-%20SameCoin.md) — [SameCoin](https://attack.mitre.org/software/S9030) can use `libexampleone.so` to fill selected files with zeros and then deletes them from the file system.(Citation: Check Point Wirte NOV 2024) [Check Point Wirte NOV 2024](https://research.checkpoint.com/2024/hamas-affiliated-threat-actor-expands-to-disruptive-activity/)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be trained on what device administrator permission request prompts look like, and how to avoid granting permissions on phishing popups.

## Sources

- [rootnik_rooting_tool](https://unit42.paloaltonetworks.com/rootnik-android-trojan-abuses-commercial-rooting-tool-and-steals-private-information/)
- [abuse_native_linux_tools](https://www.trendmicro.com/en_za/research/22/i/how-malicious-actors-abuse-native-linux-tools-in-their-attacks.html)
