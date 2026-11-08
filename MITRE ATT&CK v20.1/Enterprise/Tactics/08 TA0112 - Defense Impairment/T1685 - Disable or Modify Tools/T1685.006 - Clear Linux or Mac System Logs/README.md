# T1685.006 - Clear Linux or Mac System Logs

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1685 - Disable or Modify Tools](../README.md)

Adversaries may clear system logs to hide evidence of an intrusion. macOS and Linux both keep track of system or user-initiated actions via system logs. The majority of native system logging is stored under the `/var/log/` directory. Subfolders in this directory categorize logs by their related functions, such as:(Citation: Linux Logs)

* `/var/log/messages:`: General and system-related messages
* `/var/log/secure or /var/log/auth.log`: Authentication logs
* `/var/log/utmp or /var/log/wtmp`: Login records
* `/var/log/kern.log`: Kernel logs
* `/var/log/cron.log`: Crond logs
* `/var/log/maillog`: Mail server logs
* `/var/log/httpd/`: Web server access and error logs

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1685/006)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S1206 - JumbledPath](../../../../Threat%20Intelligence/Software/Malware/S1206%20-%20JumbledPath.md) — [JumbledPath](https://attack.mitre.org/software/S1206) can clear logs on all devices used along its connection path to compromised network infrastructure.(Citation: Cisco Salt Typhoon FEB 2025) [Cisco Salt Typhoon FEB 2025](https://blog.talosintelligence.com/salt-typhoon-analysis/)
- [S1016 - MacMa](../../../../Threat%20Intelligence/Software/Malware/S1016%20-%20MacMa.md) — [MacMa](https://attack.mitre.org/software/S1016) can clear possible malware traces such as application logs.(Citation: ESET DazzleSpy Jan 2022) [ESET DazzleSpy Jan 2022](https://www.welivesecurity.com/2022/01/25/watering-hole-deploys-new-macos-malware-dazzlespy-asia/)
- [S0279 - Proton](../../../../Threat%20Intelligence/Software/Malware/S0279%20-%20Proton.md) — [Proton](https://attack.mitre.org/software/S0279) removes logs from <code>/var/logs</code> and <code>/Library/logs</code>.(Citation: objsee mac malware 2017) [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html)
- [G0106 - Rocke](../../../../Threat%20Intelligence/Groups/G0106%20-%20Rocke.md) — [Rocke](https://attack.mitre.org/groups/G0106) has cleared log files within the /var/log/ folder.(Citation: Anomali Rocke March 2019) [Anomali Rocke March 2019](https://www.anomali.com/blog/rocke-evolves-its-arsenal-with-a-new-malware-family-written-in-golang)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has cleared logs including .bash_history, auth.log, lastlog, wtmp, and btmp.(Citation: Cisco Salt Typhoon FEB 2025) [Cisco Salt Typhoon FEB 2025](https://blog.talosintelligence.com/salt-typhoon-analysis/)
- [G1041 - Sea Turtle](../../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) has overwritten Linux system logs and unsets the Bash history file (effectively removing logging) during intrusions.(Citation: Hunt Sea Turtle 2024) [Hunt Sea Turtle 2024](https://www.huntandhackett.com/blog/turkish-espionage-campaigns)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has removed system logs from <code>/var/log/syslog</code>.(Citation: Aqua TeamTNT August 2020) [Aqua TeamTNT August 2020](https://blog.aquasec.com/container-security-tnt-container-attack)
- [S1164 - UPSTYLE](../../../../Threat%20Intelligence/Software/Malware/S1164%20-%20UPSTYLE.md) — [UPSTYLE](https://attack.mitre.org/software/S1164) clears error logs after reading embedded commands for execution.(Citation: Volexity UPSTYLE 2024) [Volexity UPSTYLE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Obfuscate/encrypt event files locally and in transit to avoid giving feedback to an adversary.
- [M1029 - Remote Data Storage](../../../../Defenses/Mitigations/M1029%20-%20Remote%20Data%20Storage.md) — Automatically forward events to a log server or data repository to prevent conditions in which the adversary can locate and manipulate data on the local system. When possible, minimize time delay on event reporting to avoid prolonged storage on the local system.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Protect generated event files that are stored locally with proper permissions and authentication and limit opportunities for adversaries to increase privileges by preventing Privilege Escalation opportunities.

## Detection strategies

- [DET0520 - Behavioral Detection of Log File Clearing on Linux and macOS](../../../../Defenses/Detection%20Strategies/DET0520%20-%20Behavioral%20Detection%20of%20Log%20File%20Clearing%20on%20Linux%20and%20macOS.md)

## Sources

- [Linux Logs](https://www.eurovps.com/blog/important-linux-log-files-you-must-be-monitoring/)
