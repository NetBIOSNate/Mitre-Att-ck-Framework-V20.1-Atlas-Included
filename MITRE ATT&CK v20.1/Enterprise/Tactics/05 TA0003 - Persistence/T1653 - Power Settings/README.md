# T1653 - Power Settings

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may impair a system's ability to hibernate, reboot, or shut down in order to extend access to infected machines. When a computer enters a dormant state, some or all software and hardware may cease to operate which can disrupt malicious activity.(Citation: Sleep, shut down, hibernate)

Adversaries may abuse system utilities and configuration settings to maintain access by preventing machines from entering a state, such as standby, that can terminate malicious activity.(Citation: Microsoft: Powercfg command-line options)(Citation: systemdsleep Linux)

For example, `powercfg` controls all configurable power system settings on a Windows system and can be abused to prevent an infected host from locking or shutting down.(Citation: Two New Monero Malware Attacks Target Windows and Android Users) Adversaries may also extend system lock screen timeout settings.(Citation: BATLOADER: The Evasive Downloader Malware) Other relevant settings, such as disk and hibernate timeout, can be similarly abused to keep the infected machine running even if no user is active.(Citation: CoinLoader: A Sophisticated Malware Loader Campaign)

Aware that some malware cannot survive system reboots, adversaries may entirely delete files used to invoke system shut down or reboot.(Citation: Condi-Botnet-binaries)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1653)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Detection strategies

- [DET0417 - Detection Strategy for Power Settings Abuse](../../../Defenses/Detection%20Strategies/DET0417%20-%20Detection%20Strategy%20for%20Power%20Settings%20Abuse.md)

## Procedure examples

- [C0046 - ArcaneDoor](../../../Threat%20Intelligence/Campaigns/C0046%20-%20ArcaneDoor.md) — [ArcaneDoor](https://attack.mitre.org/campaigns/C0046) involved exploitation of CVE-2024-20353 to force a victim Cisco ASA to reboot, triggering the automated unzipping and execution of the [Line Runner](https://attack.mitre.org/software/S1188) implant.(Citation: Cisco ArcaneDoor 2024) [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [S1186 - Line Dancer](../../../Threat%20Intelligence/Software/Malware/S1186%20-%20Line%20Dancer.md) — [Line Dancer](https://attack.mitre.org/software/S1186) can modify the crash dump process on infected machines to skip crash dump generation and proceed directly to device reboot for both persistence and forensic evasion purposes.(Citation: Cisco ArcaneDoor 2024) [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [S1188 - Line Runner](../../../Threat%20Intelligence/Software/Malware/S1188%20-%20Line%20Runner.md) — [Line Runner](https://attack.mitre.org/software/S1188) used CVE-2024-20353 to trigger victim devices to reboot, in the process unzipping and installing the [Line Dancer](https://attack.mitre.org/software/S1186) payload.(Citation: Cisco ArcaneDoor 2024) [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Periodically inspect systems for abnormal and unexpected power settings that may indicate malicious activty.

## Sources

- [Sleep, shut down, hibernate](https://www.avg.com/en/signal/should-you-shut-down-sleep-or-hibernate-your-pc-or-mac-laptop)
- [CoinLoader: A Sophisticated Malware Loader Campaign](https://www.avira.com/en/blog/coinloader-a-sophisticated-malware-loader-campaign)
- [BATLOADER: The Evasive Downloader Malware](https://blogs.vmware.com/security/2022/11/batloader-the-evasive-downloader-malware.html)
- [Two New Monero Malware Attacks Target Windows and Android Users](https://securityintelligence.com/news/two-new-monero-malware-attacks-target-windows-and-android-users/)
- [Condi-Botnet-binaries](https://www.fortinet.com/blog/threat-research/condi-ddos-botnet-spreads-via-tp-links-cve-2023-1389)
- [systemdsleep Linux](https://man7.org/linux/man-pages/man5/systemd-sleep.conf.5.html)
- [Microsoft: Powercfg command-line options](https://learn.microsoft.com/en-us/windows-hardware/design/device-experiences/powercfg-command-line-options?adlt=strict)
