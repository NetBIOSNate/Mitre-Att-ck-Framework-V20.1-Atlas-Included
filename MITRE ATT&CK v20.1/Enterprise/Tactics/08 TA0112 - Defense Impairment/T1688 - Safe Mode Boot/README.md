# T1688 - Safe Mode Boot

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may abuse Windows safe mode to disable endpoint defenses. Safe mode starts up the Windows operating system with a limited set of drivers and services. Third-party security software such as endpoint detection and response (EDR) tools may not start after booting Windows in safe mode. There are two versions of safe mode: Safe Mode and Safe Mode with Networking. It is possible to start additional services after a safe mode boot.(Citation: Microsoft Windows Startup Settings)(Citation: Sophos Safe Mode Boot)

Adversaries may abuse safe mode to disable endpoint defenses that may not start with a limited boot. Hosts can be forced into safe mode after the next reboot via modifications to Boot Configuration Data (BCD) stores, which are files that manage boot application settings.(Citation: Microsoft bcdedit)

Adversaries may also add their malicious applications to the list of minimal services that start in safe mode by modifying relevant Registry values (i.e. [Modify Registry](https://attack.mitre.org/techniques/T1112)). Malicious [Component Object Model](https://attack.mitre.org/techniques/T1559/001) (COM) objects may also be registered and loaded in safe mode.(Citation: CyberArk Labs Safe Mode 2016)(Citation: Cybereason safe mode boot)(Citation: BleepingComputer REvil 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1688)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Mitigations

- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict administrator accounts to as few individuals as possible, following least privilege principles, that may be abused to remotely boot a machine in safe mode.(Citation: CyberArk Labs Safe Mode 2016) [CyberArk Labs Safe Mode 2016](https://www.cyberark.com/resources/blog/cyberark-labs-from-safe-mode-to-domain-compromise)
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Ensure that endpoint defenses run in safe mode.(Citation: CyberArk Labs Safe Mode 2016) [CyberArk Labs Safe Mode 2016](https://www.cyberark.com/resources/blog/cyberark-labs-from-safe-mode-to-domain-compromise)

## Procedure examples

- [S1053 - AvosLocker](../../../Threat%20Intelligence/Software/Malware/S1053%20-%20AvosLocker.md) — [AvosLocker](https://attack.mitre.org/software/S1053) can restart a compromised machine in safe mode.(Citation: Trend Micro AvosLocker Apr 2022)(Citation: Costa AvosLocker May 2022) [Costa AvosLocker May 2022](https://www.linkedin.com/pulse/raas-avoslocker-incident-response-analysis-fl%C3%A1vio-costa?trk=articles_directory) · [Trend Micro AvosLocker Apr 2022](https://www.trendmicro.com/vinfo/us/security/news/ransomware-spotlight/ransomware-spotlight-avoslocker)
- [S1070 - Black Basta](../../../Threat%20Intelligence/Software/Malware/S1070%20-%20Black%20Basta.md) — [Black Basta](https://attack.mitre.org/software/S1070) can reboot victim machines in safe mode with networking via `bcdedit /set safeboot network`.(Citation: Minerva Labs Black Basta May 2022)(Citation: Cyble Black Basta May 2022)(Citation: Trend Micro Black Basta May 2022)(Citation: Avertium Black Basta June 2022)(Citation: Palo Alto Networks Black Basta August 2022) [Avertium Black Basta June 2022](https://www.avertium.com/resources/threat-reports/in-depth-look-at-black-basta-ransomware) · [Cyble Black Basta May 2022](https://web.archive.org/web/20220506143054/https://blog.cyble.com/2022/05/06/black-basta-ransomware/) · [Palo Alto Networks Black Basta August 2022](https://unit42.paloaltonetworks.com/threat-assessment-black-basta-ransomware) · [Trend Micro Black Basta May 2022](https://www.trendmicro.com/en_us/research/22/e/examining-the-black-basta-ransomwares-infection-routine.html) · [Minerva Labs Black Basta May 2022](https://minerva-labs.com/blog/new-black-basta-ransomware-hijacks-windows-fax-service/)
- [S1247 - Embargo](../../../Threat%20Intelligence/Software/Malware/S1247%20-%20Embargo.md) — [Embargo](https://attack.mitre.org/software/S1247) has used a DLL variant of MDeployer to disable security solutions through Safe Mode.(Citation: ESET Embargo Ransomware October 2024) [ESET Embargo Ransomware October 2024](https://www.welivesecurity.com/en/eset-research/embargo-ransomware-rocknrust/)
- [S1202 - LockBit 3.0](../../../Threat%20Intelligence/Software/Malware/S1202%20-%20LockBit%203.0.md) — [LockBit 3.0](https://attack.mitre.org/software/S1202) can reboot the infected host into Safe Mode.(Citation: Joint Cybersecurity Advisory LockBit 3.0 MAR 2023) [Joint Cybersecurity Advisory LockBit 3.0 MAR 2023](https://www.cisa.gov/sites/default/files/2023-03/aa23-075a-stop-ransomware-lockbit.pdf)
- [S1242 - Qilin](../../../Threat%20Intelligence/Software/Malware/S1242%20-%20Qilin.md) — [Qilin](https://attack.mitre.org/software/S1242) can reboot targeted systems in safe mode to avoid detection.(Citation: Trend Micro Agenda Ransomware AUG 2022)(Citation: BushidoToken Qilin RaaS JUN 2024) [Trend Micro Agenda Ransomware AUG 2022](https://www.trendmicro.com/en_us/research/22/h/new-golang-ransomware-agenda-customizes-attacks.html) · [BushidoToken Qilin RaaS JUN 2024](https://blog.bushidotoken.net/2024/06/tracking-adversaries-qilin-raas.html)
- [S1212 - RansomHub](../../../Threat%20Intelligence/Software/Malware/S1212%20-%20RansomHub.md) — [RansomHub](https://attack.mitre.org/software/S1212) can reboot targeted systems into Safe Mode prior to encryption.(Citation: Group-IB RansomHub FEB 2025) [Group-IB RansomHub FEB 2025](https://www.group-ib.com/blog/ransomhub-never-sleeps-episode-1/)
- [S0496 - REvil](../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) can force a reboot in safe mode with networking.(Citation: BleepingComputer REvil 2021) [BleepingComputer REvil 2021](https://www.bleepingcomputer.com/news/security/revil-ransomware-has-a-new-windows-safe-mode-encryption-mode/)

## Detection strategies

- [DET0116 - Detection Strategy for Safe Mode Boot Abuse](../../../Defenses/Detection%20Strategies/DET0116%20-%20Detection%20Strategy%20for%20Safe%20Mode%20Boot%20Abuse.md)

## Sources

- [BleepingComputer REvil 2021](https://www.bleepingcomputer.com/news/security/revil-ransomware-has-a-new-windows-safe-mode-encryption-mode/)
- [Sophos Safe Mode Boot](https://www.sophos.com/en-us/blog/snatch-ransomware-reboots-pcs-into-safe-mode-to-bypass-protection)
- [Cybereason safe mode boot](https://www.cybereason.com/blog/research/medusalocker-ransomware)
- [Microsoft Windows Startup Settings](https://support.microsoft.com/en-us/windows/windows-startup-settings-1af6ec8c-4d4a-4b23-adb7-e76eef0b847f)
- [Microsoft bcdedit](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/bcdedit)
- [CyberArk Labs Safe Mode 2016](https://www.cyberark.com/resources/blog/cyberark-labs-from-safe-mode-to-domain-compromise)
