# T1546.014 - Emond

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may gain persistence and elevate privileges by executing malicious content triggered by the Event Monitor Daemon (emond). Emond is a [Launch Daemon](https://attack.mitre.org/techniques/T1543/004) that accepts events from various services, runs them through a simple rules engine, and takes action. The emond binary at <code>/sbin/emond</code> will load any rules from the <code>/etc/emond.d/rules/</code> directory and take action once an explicitly defined event takes place.

The rule files are in the plist format and define the name, event type, and action to take. Some examples of event types include system startup and user authentication. Examples of actions are to run a system command or send an email. The emond service will not launch if there is no file present in the QueueDirectories path <code>/private/var/db/emondClients</code>, specified in the [Launch Daemon](https://attack.mitre.org/techniques/T1543/004) configuration file at<code>/System/Library/LaunchDaemons/com.apple.emond.plist</code>.(Citation: xorrior emond Jan 2018)(Citation: magnusviri emond Apr 2016)(Citation: sentinelone macos persist Jun 2019)

Adversaries may abuse this service by writing a rule to execute commands when a defined event occurs, such as system startup or user authentication.(Citation: xorrior emond Jan 2018)(Citation: magnusviri emond Apr 2016)(Citation: sentinelone macos persist Jun 2019) Adversaries may also be able to escalate privileges from administrator to root as the emond service is executed with root privileges by the [Launch Daemon](https://attack.mitre.org/techniques/T1543/004) service.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/014)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0555 - Detection Strategy for Event Triggered Execution via emond on macOS](../../../../Defenses/Detection%20Strategies/DET0555%20-%20Detection%20Strategy%20for%20Event%20Triggered%20Execution%20via%20emond%20on%20macOS.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider disabling emond by removing the [Launch Daemon](https://attack.mitre.org/techniques/T1543/004) plist file.

## Sources

- [magnusviri emond Apr 2016](http://www.magnusviri.com/Mac/what-is-emond.html)
- [xorrior emond Jan 2018](https://www.xorrior.com/emond-persistence/)
- [sentinelone macos persist Jun 2019](https://www.sentinelone.com/blog/how-malware-persists-on-macos/)
