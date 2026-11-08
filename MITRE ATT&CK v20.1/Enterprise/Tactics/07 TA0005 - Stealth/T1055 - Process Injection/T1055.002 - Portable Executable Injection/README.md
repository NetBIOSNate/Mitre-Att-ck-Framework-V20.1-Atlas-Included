# T1055.002 - Portable Executable Injection

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject portable executables (PE) into processes in order to evade process-based defenses as well as possibly elevate privileges. PE injection is a method of executing arbitrary code in the address space of a separate live process. 

PE injection is commonly performed by copying code (perhaps without a file on disk) into the virtual address space of the target process before invoking it via a new thread. The write can be performed with native Windows API calls such as <code>VirtualAllocEx</code> and <code>WriteProcessMemory</code>, then invoked with <code>CreateRemoteThread</code> or additional code (ex: shellcode). The displacement of the injected code does introduce the additional requirement for functionality to remap memory references.(Citation: Elastic Process Injection July 2017) 

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via PE injection may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/002)

**Tactics**  [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0057 - 3CX Supply Chain Attack](../../../../Threat%20Intelligence/Campaigns/C0057%20-%203CX%20Supply%20Chain%20Attack.md) — During the [3CX Supply Chain Attack](https://attack.mitre.org/campaigns/C0057), [AppleJeus](https://attack.mitre.org/groups/G1049) uses the SigFlip tool to inject arbitrary code without affecting or breaking the file's signature.(Citation: GitHub SigFlip opensource tool)(Citation: Mandiant 3cx UNC4736 2023) [Mandiant 3cx UNC4736 2023](https://cloud.google.com/blog/topics/threat-intelligence/3cx-software-supply-chain-compromise/) · [GitHub SigFlip opensource tool](https://github.com/med0x2e/SigFlip)
- [S1063 - Brute Ratel C4](../../../../Threat%20Intelligence/Software/Tools/S1063%20-%20Brute%20Ratel%20C4.md) — [Brute Ratel C4](https://attack.mitre.org/software/S1063) has injected [Latrodectus](https://attack.mitre.org/software/S1160) into the Explorer.exe process on comrpomised hosts.(Citation: Rapid7 Fake W2 July 2024) [Rapid7 Fake W2 July 2024](https://www.rapid7.com/blog/post/2024/07/24/malware-campaign-lures-users-with-fake-w2-form/)
- [S0030 - Carbanak](../../../../Threat%20Intelligence/Software/Malware/S0030%20-%20Carbanak.md) — [Carbanak](https://attack.mitre.org/software/S0030) downloads an executable and injects it directly into a new process.(Citation: FireEye CARBANAK June 2017) [FireEye CARBANAK June 2017](https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html)
- [S1158 - DUSTPAN](../../../../Threat%20Intelligence/Software/Malware/S1158%20-%20DUSTPAN.md) — [DUSTPAN](https://attack.mitre.org/software/S1158) can inject its decrypted payload into another process.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
- [S1138 - Gootloader](../../../../Threat%20Intelligence/Software/Malware/S1138%20-%20Gootloader.md) — [Gootloader](https://attack.mitre.org/software/S1138) can use its own PE loader to execute payloads in memory.(Citation: Sophos Gootloader) [Sophos Gootloader](https://news.sophos.com/en-us/2021/03/01/gootloader-expands-its-payload-delivery-options/)
- [G0078 - Gorgon Group](../../../../Threat%20Intelligence/Groups/G0078%20-%20Gorgon%20Group.md) — [Gorgon Group](https://attack.mitre.org/groups/G0078) malware can download a remote access tool, [ShiftyBug](https://attack.mitre.org/software/S0294), and inject into another process.(Citation: Unit 42 Gorgon Group Aug 2018) [Unit 42 Gorgon Group Aug 2018](https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/)
- [S0342 - GreyEnergy](../../../../Threat%20Intelligence/Software/Malware/S0342%20-%20GreyEnergy.md) — [GreyEnergy](https://attack.mitre.org/software/S0342) has a module to inject a PE binary into a remote process.(Citation: ESET GreyEnergy Oct 2018) [ESET GreyEnergy Oct 2018](https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf)
- [S1229 - Havoc](../../../../Threat%20Intelligence/Software/Malware/S1229%20-%20Havoc.md) — [Havoc](https://attack.mitre.org/software/S1229) has itself injected into `C:\\Windows\\System32\\Werfault.exe` on targeted systems.(Citation: Havoc Framework Documentation) [Havoc Framework Documentation](https://havocframework.com/docs/welcome)
- [S0260 - InvisiMole](../../../../Threat%20Intelligence/Software/Malware/S0260%20-%20InvisiMole.md) — [InvisiMole](https://attack.mitre.org/software/S0260) can inject its backdoor as a portable executable into a target process.(Citation: ESET InvisiMole June 2020) [ESET InvisiMole June 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_InvisiMole.pdf)
- [S0681 - Lizar](../../../../Threat%20Intelligence/Software/Malware/S0681%20-%20Lizar.md) — [Lizar](https://attack.mitre.org/software/S0681) can execute PE files in the address space of the specified process.(Citation: BiZone Lizar May 2021) [BiZone Lizar May 2021](https://bi-zone.medium.com/from-pentest-to-apt-attack-cybercriminal-group-fin7-disguises-its-malware-as-an-ethical-hackers-c23c9a75e319)
- [S1145 - Pikabot](../../../../Threat%20Intelligence/Software/Malware/S1145%20-%20Pikabot.md) — [Pikabot](https://attack.mitre.org/software/S1145), following payload decryption, creates a process hard-coded into the dropped (e.g., WerFault.exe) and injects the decrypted core modules into it.(Citation: Zscaler Pikabot 2023) [Zscaler Pikabot 2023](https://www.zscaler.com/blogs/security-research/technical-analysis-pikabot)
- [G0106 - Rocke](../../../../Threat%20Intelligence/Groups/G0106%20-%20Rocke.md) — [Rocke](https://attack.mitre.org/groups/G0106)'s miner, "TermsHost.exe", evaded defenses by injecting itself into Windows processes, including Notepad.exe.(Citation: Talos Rocke August 2018) [Talos Rocke August 2018](https://blog.talosintelligence.com/2018/08/rocke-champion-of-monero-miners.html)
- [S9037 - RustyWater](../../../../Threat%20Intelligence/Software/Malware/S9037%20-%20RustyWater.md) — [RustyWater](https://attack.mitre.org/software/S9037) has injected its shellcode into explorer.exe by allocating memory via `VirtualAllocEx`, then by writing the payload via `WriteProcessMemory`.(Citation: CloudSEK_RustyWater_Jan2026) [CloudSEK_RustyWater_Jan2026](https://www.cloudsek.com/blog/reborn-in-rust-muddywater-evolves-tooling-with-rustywater-implant)
- [S9024 - SPAWNCHIMERA](../../../../Threat%20Intelligence/Software/Malware/S9024%20-%20SPAWNCHIMERA.md) — [SPAWNCHIMERA](https://attack.mitre.org/software/S9024) has executed only in memory and hooked itself into existing processes on the victim device to include the web process.(Citation: CISA SPAWNCHIMERA RESURGE February 2026)(Citation: Google UNC5221 BRICKSTORM SPAWNCHIMERA April 2024)(Citation: JPCERT SPAWNCHIMERA Ivanti February 2025) [CISA SPAWNCHIMERA RESURGE February 2026](https://www.cisa.gov/news-events/analysis-reports/ar25-087a) · [Google UNC5221 BRICKSTORM SPAWNCHIMERA April 2024](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-post-exploitation-lateral-movement) · [JPCERT SPAWNCHIMERA Ivanti February 2025](https://blogs.jpcert.or.jp/en/2025/02/spawnchimera.html)
- [S0330 - Zeus Panda](../../../../Threat%20Intelligence/Software/Malware/S0330%20-%20Zeus%20Panda.md) — [Zeus Panda](https://attack.mitre.org/software/S0330) checks processes on the system and if they meet the necessary requirements, it injects into that process.(Citation: GDATA Zeus Panda June 2017) [GDATA Zeus Panda June 2017](https://cyberwtf.files.wordpress.com/2017/07/panda-whitepaper.pdf)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.

## Detection strategies

- [DET0106 - Behavioral Detection of PE Injection via Remote Memory Mapping](../../../../Defenses/Detection%20Strategies/DET0106%20-%20Behavioral%20Detection%20of%20PE%20Injection%20via%20Remote%20Memory%20Mapping.md)

## Sources

- [Elastic Process Injection July 2017](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
