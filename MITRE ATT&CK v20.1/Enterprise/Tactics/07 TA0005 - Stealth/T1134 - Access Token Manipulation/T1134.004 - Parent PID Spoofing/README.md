# T1134.004 - Parent PID Spoofing

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1134 - Access Token Manipulation](../README.md)

Adversaries may spoof the parent process identifier (PPID) of a new process to evade process-monitoring defenses or to elevate privileges. New processes are typically spawned directly from their parent, or calling, process unless explicitly specified. One way of explicitly assigning the PPID of a new process is via the <code>CreateProcess</code> API call, which supports a parameter that defines the PPID to use.(Citation: DidierStevens SelectMyParent Nov 2009) This functionality is used by Windows features such as User Account Control (UAC) to correctly set the PPID after a requested elevated process is spawned by SYSTEM (typically via <code>svchost.exe</code> or <code>consent.exe</code>) rather than the current user context.(Citation: Microsoft UAC Nov 2018)

Adversaries may abuse these mechanisms to evade defenses, such as those blocking processes spawning directly from Office documents, and analysis targeting unusual/potentially malicious parent-child process relationships, such as spoofing the PPID of [PowerShell](https://attack.mitre.org/techniques/T1059/001)/[Rundll32](https://attack.mitre.org/techniques/T1218/011) to be <code>explorer.exe</code> rather than an Office document delivered as part of [Spearphishing Attachment](https://attack.mitre.org/techniques/T1566/001).(Citation: CounterCept PPID Spoofing Dec 2018) This spoofing could be executed via [Visual Basic](https://attack.mitre.org/techniques/T1059/005) within a malicious Office document or any code that can perform [Native API](https://attack.mitre.org/techniques/T1106).(Citation: CTD PPID Spoofing Macro Mar 2019)(Citation: CounterCept PPID Spoofing Dec 2018)

Explicitly assigning the PPID may also enable elevated privileges given appropriate access rights to the parent process. For example, an adversary in a privileged user context (i.e. administrator) may spawn a new process and assign the parent as a process running as SYSTEM (such as <code>lsass.exe</code>), causing the new process to be elevated via the inherited access token.(Citation: XPNSec PPID Nov 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1134/004)

**Tactics**  [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) can spawn processes with alternate PPIDs.(Citation: CobaltStrike Daddy May 2017)(Citation: Cobalt Strike Manual 4.3 November 2020) [CobaltStrike Daddy May 2017](https://web.archive.org/web/20171009220105/https://blog.cobaltstrike.com/2017/05/23/cobalt-strike-3-8-whos-your-daddy/) · [Cobalt Strike Manual 4.3 November 2020](https://web.archive.org/web/20210708035426/https://www.cobaltstrike.com/downloads/csmanual43.pdf)
- [S1111 - DarkGate](../../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) relies on parent PID spoofing as part of its "rootkit-like" functionality to evade detection via Task Manager or Process Explorer.(Citation: Trellix Darkgate 2023) [Trellix Darkgate 2023](https://www.trellix.com/blogs/research/the-continued-evolution-of-the-darkgate-malware-as-a-service/)
- [S0356 - KONNI](../../../../Threat%20Intelligence/Software/Malware/S0356%20-%20KONNI.md) — [KONNI](https://attack.mitre.org/software/S0356) has used parent PID spoofing to spawn a new `cmd` process using `CreateProcessW` and a handle to `Taskmgr.exe`.(Citation: Malwarebytes Konni Aug 2021) [Malwarebytes Konni Aug 2021](https://blog.malwarebytes.com/threat-intelligence/2021/08/new-variant-of-konni-malware-used-in-campaign-targetting-russia/)
- [S0501 - PipeMon](../../../../Threat%20Intelligence/Software/Malware/S0501%20-%20PipeMon.md) — [PipeMon](https://attack.mitre.org/software/S0501) can use parent PID spoofing to elevate privileges.(Citation: ESET PipeMon May 2020) [ESET PipeMon May 2020](https://www.welivesecurity.com/2020/05/21/no-game-over-winnti-group/)

## Detection strategies

- [DET0489 - Behavior-chain detection for T1134.004 Access Token Manipulation: Parent PID Spoofing (Windows)](../../../../Defenses/Detection%20Strategies/DET0489%20-%20Behavior-chain%20detection%20for%20T1134.004%20Access%20Token%20Manipulation%20-%20Parent%20PID%20Spoofin.md)

## Sources

- [XPNSec PPID Nov 2017](https://blog.xpnsec.com/becoming-system/)
- [CounterCept PPID Spoofing Dec 2018](https://web.archive.org/web/20200726110643/https://blog.f-secure.com/detecting-parent-pid-spoofing/)
- [Microsoft UAC Nov 2018](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works)
- [DidierStevens SelectMyParent Nov 2009](https://blog.didierstevens.com/2009/11/22/quickpost-selectmyparent-or-playing-with-the-windows-process-tree/)
- [CTD PPID Spoofing Macro Mar 2019](https://blog.christophetd.fr/building-an-office-macro-to-spoof-process-parent-and-command-line/)
