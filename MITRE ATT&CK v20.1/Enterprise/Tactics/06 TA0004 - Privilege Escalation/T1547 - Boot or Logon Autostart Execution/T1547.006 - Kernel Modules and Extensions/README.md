# T1547.006 - Kernel Modules and Extensions

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may modify the kernel to automatically execute programs on system boot. Loadable Kernel Modules (LKMs) are pieces of code that can be loaded and unloaded into the kernel upon demand. They extend the functionality of the kernel without the need to reboot the system. For example, one type of module is the device driver, which allows the kernel to access hardware connected to the system.(Citation: Linux Kernel Programming) 

When used maliciously, LKMs can be a type of kernel-mode [Rootkit](https://attack.mitre.org/techniques/T1014) that run with the highest operating system privilege (Ring 0).(Citation: Linux Kernel Module Programming Guide) Common features of LKM based rootkits include: hiding itself, selective hiding of files, processes and network activity, as well as log tampering, providing authenticated backdoors, and enabling root access to non-privileged users.(Citation: iDefense Rootkit Overview)

Kernel extensions, also called kext, are used in macOS to load functionality onto a system similar to LKMs for Linux. Since the kernel is responsible for enforcing security and the kernel extensions run as apart of the kernel, kexts are not governed by macOS security policies. Kexts are loaded and unloaded through <code>kextload</code> and <code>kextunload</code> commands. Kexts need to be signed with a developer ID that is granted privileges by Apple allowing it to sign Kernel extensions. Developers without these privileges may still sign kexts but they will not load unless SIP is disabled. If SIP is enabled, the kext signature is verified before being added to the AuxKC.(Citation: System and kernel extensions in macOS)

Since macOS Catalina 10.15, kernel extensions have been deprecated in favor of System Extensions. However, kexts are still allowed as "Legacy System Extensions" since there is no System Extension for Kernel Programming Interfaces.(Citation: Apple Kernel Extension Deprecation)

Adversaries can use LKMs and kexts to conduct [Persistence](https://attack.mitre.org/tactics/TA0003) and/or [Privilege Escalation](https://attack.mitre.org/tactics/TA0004) on a system. Examples have been found in the wild, and there are some relevant open source projects as well.(Citation: Volatility Phalanx2)(Citation: CrowdStrike Linux Rootkit)(Citation: GitHub Reptile)(Citation: GitHub Diamorphine)(Citation: RSAC 2015 San Francisco Patrick Wardle)(Citation: Synack Secure Kernel Extension Broken)(Citation: Securelist Ventir)(Citation: Trend Micro Skidmap)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/006)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md), [Linux](../../../../Platforms/Linux.md)

## Detection strategies

- [DET0450 - Detection Strategy for Kernel Modules and Extensions Autostart Execution](../../../../Defenses/Detection%20Strategies/DET0450%20-%20Detection%20Strategy%20for%20Kernel%20Modules%20and%20Extensions%20Autostart%20Execution.md)

## Procedure examples

- [S0502 - Drovorub](../../../../Threat%20Intelligence/Software/Malware/S0502%20-%20Drovorub.md) — [Drovorub](https://attack.mitre.org/software/S0502) can use kernel modules to establish persistence.(Citation: NSA/FBI Drovorub August 2020) [NSA/FBI Drovorub August 2020](https://media.defense.gov/2020/Aug/13/2002476465/-1/-1/0/CSA_DROVORUB_RUSSIAN_GRU_MALWARE_AUG_2020.PDF)
- [C0012 - Operation CuckooBees](../../../../Threat%20Intelligence/Campaigns/C0012%20-%20Operation%20CuckooBees.md) — During [Operation CuckooBees](https://attack.mitre.org/campaigns/C0012), attackers used a signed kernel rootkit to establish additional persistence.(Citation: Cybereason OperationCuckooBees May 2022) [Cybereason OperationCuckooBees May 2022](https://www.cybereason.com/blog/operation-cuckoobees-deep-dive-into-stealthy-winnti-techniques)
- [S1219 - REPTILE](../../../../Threat%20Intelligence/Software/Malware/S1219%20-%20REPTILE.md) — The [REPTILE](https://attack.mitre.org/software/S1219) rootkit is implemented as a loadable kernel module (LKM).(Citation: Google Cloud Mandiant UNC3886 2024) [Google Cloud Mandiant UNC3886 2024](https://cloud.google.com/blog/topics/threat-intelligence/uncovering-unc3886-espionage-operations)
- [S0468 - Skidmap](../../../../Threat%20Intelligence/Software/Malware/S0468%20-%20Skidmap.md) — [Skidmap](https://attack.mitre.org/software/S0468) has the ability to install several loadable kernel modules (LKMs) on infected machines.(Citation: Trend Micro Skidmap) [Trend Micro Skidmap](https://blog.trendmicro.com/trendlabs-security-intelligence/skidmap-linux-malware-uses-rootkit-capabilities-to-hide-cryptocurrency-mining-payload/)

## Mitigations

- [M1049 - Antivirus/Antimalware](../../../../Defenses/Mitigations/M1049%20-%20Antivirus%20-%20Antimalware.md) — Common tools for detecting Linux rootkits include: rkhunter (Citation: SourceForge rkhunter), chrootkit (Citation: Chkrootkit Main), although rootkits may be designed to evade certain detection tools. [SourceForge rkhunter](http://rkhunter.sourceforge.net) · [Chkrootkit Main](http://www.chkrootkit.org/)
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Application control and software restriction tools, such as SELinux, KSPP, grsecurity MODHARDEN, and Linux kernel tuning can aid in restricting kernel module loading.(Citation: Kernel.org Restrict Kernel Module)(Citation: Wikibooks Grsecurity)(Citation: Kernel Self Protection Project)(Citation: Increasing Linux kernel integrity)(Citation: LKM loading kernel restrictions) [Increasing Linux kernel integrity](https://linux-audit.com/increase-kernel-integrity-with-disabled-linux-kernel-modules-loading/) · [Kernel Self Protection Project](https://www.kernel.org/doc/html/latest/security/self-protection.html) · [LKM loading kernel restrictions](https://xorl.wordpress.com/2018/02/17/lkm-loading-kernel-restrictions/) · [Kernel.org Restrict Kernel Module](https://patchwork.kernel.org/patch/8754821/) · [Wikibooks Grsecurity](https://en.wikibooks.org/wiki/Grsecurity/The_RBAC_System)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit access to the root account and prevent users from loading kernel modules and extensions through proper privilege separation and limiting Privilege Escalation opportunities.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Use MDM to disable user's ability to install or approve kernel extensions, and ensure all approved kernel extensions are in alignment with policies specified in <code>com.apple.syspolicy.kernel-extension-policy</code>.(Citation: Apple TN2459 Kernel Extensions)(Citation: MDMProfileConfigMacOS) [Apple TN2459 Kernel Extensions](https://developer.apple.com/library/archive/technotes/tn2459/_index.html) · [MDMProfileConfigMacOS](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)

## Sources

- [Apple Developer Configuration Profile](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
- [Apple Kernel Extension Deprecation](https://developer.apple.com/support/kernel-extensions/)
- [System and kernel extensions in macOS](https://support.apple.com/guide/deployment/system-and-kernel-extensions-in-macos-depa5fb8376f/web)
- [GitHub Reptile](https://github.com/f0rb1dd3n/Reptile)
- [Volatility Phalanx2](https://volatility-labs.blogspot.com/2012/10/phalanx-2-revealed-using-volatility-to.html)
- [iDefense Rootkit Overview](https://www.megasecurity.org/papers/Rootkits.pdf)
- [Linux Loadable Kernel Module Insert and Remove LKMs](https://tldp.org/HOWTO/Module-HOWTO/x197.html)
- [CrowdStrike Linux Rootkit](https://www.crowdstrike.com/blog/http-iframe-injecting-linux-rootkit/)
- [GitHub Diamorphine](https://github.com/m0nad/Diamorphine)
- [Securelist Ventir](https://securelist.com/the-ventir-trojan-assemble-your-macos-spy/67267/)
- [User Approved Kernel Extension Pike’s](https://pikeralpha.wordpress.com/2017/08/29/user-approved-kernel-extension-loading/)
- [Linux Kernel Module Programming Guide](https://tldp.org/LDP/lkmpg/2.4/html/x437.html)
- [Linux Kernel Programming](https://www.tldp.org/LDP/lkmpg/2.4/lkmpg.pdf)
- [Trend Micro Skidmap](https://blog.trendmicro.com/trendlabs-security-intelligence/skidmap-linux-malware-uses-rootkit-capabilities-to-hide-cryptocurrency-mining-payload/)
- [Purves Kextpocalypse 2](https://richard-purves.com/2017/11/09/mdm-and-the-kextpocalypse-2/)
- [RSAC 2015 San Francisco Patrick Wardle](https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf)
- [Synack Secure Kernel Extension Broken](https://objective-see.org/blog/blog_0x21.html)
- [Wikipedia Loadable Kernel Module](https://en.wikipedia.org/wiki/Loadable_kernel_module#Linux)
