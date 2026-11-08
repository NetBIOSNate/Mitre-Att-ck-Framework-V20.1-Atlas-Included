# T1569.001 - Launchctl

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1569 - System Services](../README.md)

Adversaries may abuse launchctl to execute commands or programs. Launchctl interfaces with launchd, the service management framework for macOS. Launchctl supports taking subcommands on the command-line, interactively, or even redirected from standard input.(Citation: Launchctl Man)

Adversaries use launchctl to execute commands and programs as [Launch Agent](https://attack.mitre.org/techniques/T1543/001)s or [Launch Daemon](https://attack.mitre.org/techniques/T1543/004)s. Common subcommands include: <code>launchctl load</code>,<code>launchctl unload</code>, and <code>launchctl start</code>. Adversaries can use scripts or manually run the commands <code>launchctl load -w "%s/Library/LaunchAgents/%s"</code> or <code>/bin/launchctl load</code> to execute [Launch Agent](https://attack.mitre.org/techniques/T1543/001)s or [Launch Daemon](https://attack.mitre.org/techniques/T1543/004)s.(Citation: Sofacy Komplex Trojan)(Citation: 20 macOS Common Tools and Techniques)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1569/001)

**Tactics**  [Execution](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0584 - AppleJeus](../../../../Threat%20Intelligence/Software/Malware/S0584%20-%20AppleJeus.md) — [AppleJeus](https://attack.mitre.org/software/S0584) has loaded a plist file using the <code>launchctl</code> command.(Citation: CISA AppleJeus Feb 2021) [CISA AppleJeus Feb 2021](https://us-cert.cisa.gov/ncas/alerts/aa21-048a)
- [S0274 - Calisto](../../../../Threat%20Intelligence/Software/Malware/S0274%20-%20Calisto.md) — [Calisto](https://attack.mitre.org/software/S0274) uses launchctl to enable screen sharing on the victim’s machine.(Citation: Securelist Calisto July 2018) [Securelist Calisto July 2018](https://securelist.com/calisto-trojan-for-macos/86543/)
- [S1153 - Cuckoo Stealer](../../../../Threat%20Intelligence/Software/Malware/S1153%20-%20Cuckoo%20Stealer.md) — [Cuckoo Stealer](https://attack.mitre.org/software/S1153) can use `launchctl` to load a LaunchAgent for persistence.(Citation: Kandji Cuckoo April 2024) [Kandji Cuckoo April 2024](https://www.kandji.io/blog/malware-cuckoo-infostealer-spyware)
- [S0451 - LoudMiner](../../../../Threat%20Intelligence/Software/Malware/S0451%20-%20LoudMiner.md) — [LoudMiner](https://attack.mitre.org/software/S0451) launched the QEMU services in the <code>/Library/LaunchDaemons/</code> folder using <code>launchctl</code>. It also uses <code>launchctl</code> to unload all [Launch Daemon](https://attack.mitre.org/techniques/T1543/004)s when updating to a newer version of [LoudMiner](https://attack.mitre.org/software/S0451).(Citation: ESET LoudMiner June 2019) [ESET LoudMiner June 2019](https://www.welivesecurity.com/2019/06/20/loudminer-mining-cracked-vst-software/)
- [S1048 - macOS.OSAMiner](../../../../Threat%20Intelligence/Software/Malware/S1048%20-%20macOS.OSAMiner.md) — [macOS.OSAMiner](https://attack.mitre.org/software/S1048) has used `launchctl` to restart the [Launch Agent](https://attack.mitre.org/techniques/T1543/001).(Citation: SentinelLabs reversing run-only applescripts 2021) [SentinelLabs reversing run-only applescripts 2021](https://www.sentinelone.com/labs/fade-dead-adventures-in-reversing-malicious-run-only-applescripts/)
- [S0658 - XCSSET](../../../../Threat%20Intelligence/Software/Malware/S0658%20-%20XCSSET.md) — [XCSSET](https://attack.mitre.org/software/S0658) loads a system level launchdaemon using the <code>launchctl load -w</code> command from <code>/System/Librarby/LaunchDaemons/ssh.plist</code>.(Citation: trendmicro xcsset xcode project 2020) [trendmicro xcsset xcode project 2020](https://documents.trendmicro.com/assets/pdf/XCSSET_Technical_Brief.pdf)

## Detection strategies

- [DET0265 - Detection Strategy for System Services: Launchctl](../../../../Defenses/Detection%20Strategies/DET0265%20-%20Detection%20Strategy%20for%20System%20Services%20-%20Launchctl.md)

## Mitigations

- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Prevent users from installing their own launch agents or launch daemons.

## Sources

- [Sofacy Komplex Trojan](https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/)
- [20 macOS Common Tools and Techniques](https://labs.sentinelone.com/20-common-tools-techniques-used-by-macos-threat-actors-malware/)
- [Launchctl Man](https://ss64.com/osx/launchctl.html)
