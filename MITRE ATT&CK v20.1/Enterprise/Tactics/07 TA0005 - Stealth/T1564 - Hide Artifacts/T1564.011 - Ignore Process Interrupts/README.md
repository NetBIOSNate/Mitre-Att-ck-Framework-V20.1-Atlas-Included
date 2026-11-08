# T1564.011 - Ignore Process Interrupts

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1564 - Hide Artifacts](../README.md)

Adversaries may evade defensive mechanisms by executing commands that hide from process interrupt signals. Many operating systems use signals to deliver messages to control process behavior. Command interpreters often include specific commands/flags that ignore errors and other hangups, such as when the user of the active session logs off.(Citation: Linux Signal Man)  These interrupt signals may also be used by defensive tools and/or analysts to pause or terminate specified running processes. 

Adversaries may invoke processes using `nohup`, [PowerShell](https://attack.mitre.org/techniques/T1059/001) `-ErrorAction SilentlyContinue`, or similar commands that may be immune to hangups.(Citation: nohup Linux Man)(Citation: Microsoft PowerShell SilentlyContinue) This may enable malicious commands and malware to continue execution through system events that would otherwise terminate its execution, such as users logging off or the termination of its C2 network connection.

Hiding from process interrupt signals may allow malware to continue execution, but unlike [Trap](https://attack.mitre.org/techniques/T1546/005) this does not establish [Persistence](https://attack.mitre.org/tactics/TA0003) since the process will not be re-invoked once actually terminated.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564/011)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has used remote access tools that run AppleScript using ` nohup osascript` to ignore hangup signals.(Citation: Microsoft Axios Compromise APR 2026) [Microsoft Axios Compromise APR 2026](https://www.microsoft.com/en-us/security/blog/2026/04/01/mitigating-the-axios-npm-supply-chain-compromise/)
- [S1184 - BOLDMOVE](../../../../Threat%20Intelligence/Software/Malware/S1184%20-%20BOLDMOVE.md) — [BOLDMOVE](https://attack.mitre.org/software/S1184) calls the signal function to ignore the signals SIGCHLD, SIGHIP, and SIGPIPE prior to starting primary logic.(Citation: Google Cloud BOLDMOVE 2023) [Google Cloud BOLDMOVE 2023](https://cloud.google.com/blog/topics/threat-intelligence/chinese-actors-exploit-fortios-flaw/)
- [S1161 - BPFDoor](../../../../Threat%20Intelligence/Software/Malware/S1161%20-%20BPFDoor.md) — [BPFDoor](https://attack.mitre.org/software/S1161) sets its process to ignore the following signals; `SIGHUP`, `SIGINT`, `SIGQUIT`, `SIGPIPE`, `SIGCHLD`, `SIGTTIN`, and `SIGTTOU`.(Citation: Deep Instinct BPFDoor 2023) [Deep Instinct BPFDoor 2023](https://www.deepinstinct.com/blog/bpfdoor-malware-evolves-stealthy-sniffing-backdoor-ups-its-game)
- [S0588 - GoldMax](../../../../Threat%20Intelligence/Software/Malware/S0588%20-%20GoldMax.md) — The [GoldMax](https://attack.mitre.org/software/S0588) Linux variant has been executed with the `nohup` command to ignore hangup signals and continue to run if the terminal session was terminated.(Citation: CrowdStrike StellarParticle January 2022) [CrowdStrike StellarParticle January 2022](https://www.crowdstrike.com/blog/observations-from-the-stellarparticle-campaign/)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has leveraged the PowerShell `-ErrorAction SilentlyContinue` command to continue execution through system events.(Citation: Aryaka Kimsuky July 2025) [Aryaka Kimsuky July 2025](https://www.aryaka.com/docs/reports/aryaka-kimsuky-apt-operational-blueprint.pdf)
- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has suppressed output so that nothing is printed to terminal and has utilized silent exiting when environmental variables match restricted values.(Citation: Hunt.io TeamPCP Toolkit MAY 2026) [Hunt.io TeamPCP Toolkit MAY 2026](https://hunt.io/blog/teampcp-python-toolkit-firescale-github-c2-takedown)
- [S0402 - OSX/Shlayer](../../../../Threat%20Intelligence/Software/Malware/S0402%20-%20OSX%20-%20Shlayer.md) — [OSX/Shlayer](https://attack.mitre.org/software/S0402) has used the `nohup` command to instruct executed payloads to ignore hangup signals.(Citation: Shlayer jamf gatekeeper bypass 2021) [Shlayer jamf gatekeeper bypass 2021](https://www.jamf.com/blog/shlayer-malware-abusing-gatekeeper-bypass-on-macos/)
- [G1041 - Sea Turtle](../../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) executed [SnappyTCP](https://attack.mitre.org/software/S1163) using the tool NoHup, which keeps the malware running on a system after exiting the shell or terminal.(Citation: Hunt Sea Turtle 2024) [Hunt Sea Turtle 2024](https://www.huntandhackett.com/blog/turkish-espionage-campaigns)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has suppressed NPM warnings by silently exiting through the use of the NPM success code that has a setting that all errors exit with `code 0`.(Citation: Socket Shai-Hulud November 2025) [Socket Shai-Hulud November 2025](https://socket.dev/blog/shai-hulud-strikes-again-v2)
- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) modified the startup file `/etc/init.d/localnet` to execute the line `nohup /bin/support &` so the script would run when the system was rebooted.(Citation: Mandiant Fortinet Zero Day) [Mandiant Fortinet Zero Day](https://www.mandiant.com/resources/blog/fortinet-malware-ecosystem)

## Detection strategies

- [DET0067 - Detection Strategy for Ignore Process Interrupts](../../../../Defenses/Detection%20Strategies/DET0067%20-%20Detection%20Strategy%20for%20Ignore%20Process%20Interrupts.md)

## Sources

- [Linux Signal Man](https://man7.org/linux/man-pages/man7/signal.7.html)
- [nohup Linux Man](https://linux.die.net/man/1/nohup)
- [Microsoft PowerShell SilentlyContinue](https://learn.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-7.3#debugpreference)
