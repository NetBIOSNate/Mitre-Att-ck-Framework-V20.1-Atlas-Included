# T1543.002 - Systemd Service

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1543 - Create or Modify System Process](../README.md)

Adversaries may create or modify systemd services to repeatedly execute malicious payloads as part of persistence. Systemd is a system and service manager commonly used for managing background daemon processes (also known as services) and other system resources.(Citation: Linux man-pages: systemd January 2014) Systemd is the default initialization (init) system on many Linux distributions replacing legacy init systems, including SysVinit and Upstart, while remaining backwards compatible.  

Systemd utilizes unit configuration files with the `.service` file extension to encode information about a service's process. By default, system level unit files are stored in the `/systemd/system` directory of the root owned directories (`/`). User level unit files are stored in the `/systemd/user` directories of the user owned directories (`$HOME`).(Citation: lambert systemd 2022) 

Inside the `.service` unit files, the following directives are used to execute commands:(Citation: freedesktop systemd.service)  

* `ExecStart`, `ExecStartPre`, and `ExecStartPost` directives execute when a service is started manually by `systemctl` or on system start if the service is set to automatically start.
* `ExecReload` directive executes when a service restarts. 
* `ExecStop`, `ExecStopPre`, and `ExecStopPost` directives execute when a service is stopped.  

Adversaries have created new service files, altered the commands a `.service` file’s directive executes, and modified the user directive a `.service` file executes as, which could result in privilege escalation. Adversaries may also place symbolic links in these directories, enabling systemd to find these payloads regardless of where they reside on the filesystem.(Citation: Anomali Rocke March 2019)(Citation: airwalk backdoor unix systems)(Citation: Rapid7 Service Persistence 22JUNE2016) 

The `.service` file’s User directive can be used to run service as a specific user, which could result in privilege escalation based on specific user/group permissions. 

Systemd services can be created via systemd generators, which support the dynamic generation of unit files. Systemd generators are small executables that run during boot or configuration reloads to dynamically create or modify systemd unit files by converting non-native configurations into services, symlinks, or drop-ins (i.e., [Boot or Logon Initialization Scripts](https://attack.mitre.org/techniques/T1037)).(Citation: Elastic Security Labs Linux Persistence 2024)(Citation: Pepe Berba Systemd 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1543/002)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Detection strategies

- [DET0253 - Detection of Systemd Service Creation or Modification on Linux](../../../../Defenses/Detection%20Strategies/DET0253%20-%20Detection%20of%20Systemd%20Service%20Creation%20or%20Modification%20on%20Linux.md)

## Procedure examples

- [C0034 - 2022 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0034%20-%202022%20Ukraine%20Electric%20Power%20Attack.md) — During the [2022 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0034), [Sandworm Team](https://attack.mitre.org/groups/G0034) configured Systemd to maintain persistence of GOGETTER, specifying the `WantedBy=multi-user.target` configuration to run GOGETTER when the system begins accepting user logins.(Citation: Mandiant-Sandworm-Ukraine-2022) [Mandiant-Sandworm-Ukraine-2022](https://www.mandiant.com/resources/blog/sandworm-disrupts-power-ukraine-operational-technology)
- [S0401 - Exaramel for Linux](../../../../Threat%20Intelligence/Software/Malware/S0401%20-%20Exaramel%20for%20Linux.md) — [Exaramel for Linux](https://attack.mitre.org/software/S0401) has a hardcoded location under systemd that it uses to achieve persistence if it is running as root.(Citation: ESET TeleBots Oct 2018)(Citation: ANSSI Sandworm January 2021) [ESET TeleBots Oct 2018](https://www.welivesecurity.com/2018/10/11/new-telebots-backdoor-linking-industroyer-notpetya/) · [ANSSI Sandworm January 2021](https://www.cert.ssi.gouv.fr/uploads/CERTFR-2021-CTI-005.pdf)
- [S0410 - Fysbis](../../../../Threat%20Intelligence/Software/Malware/S0410%20-%20Fysbis.md) — [Fysbis](https://attack.mitre.org/software/S0410) has established persistence using a systemd service.(Citation: Fysbis Dr Web Analysis) [Fysbis Dr Web Analysis](https://vms.drweb.com/virus/?i=4276269)
- [S1198 - Gomir](../../../../Threat%20Intelligence/Software/Malware/S1198%20-%20Gomir.md) — [Gomir](https://attack.mitre.org/software/S1198) creates a systemd service named `syslogd` for persistence.(Citation: Symantec Troll Stealer 2024) [Symantec Troll Stealer 2024](https://www.security.com/threat-intelligence/springtail-kimsuky-backdoor-espionage)
- [S0601 - Hildegard](../../../../Threat%20Intelligence/Software/Malware/S0601%20-%20Hildegard.md) — [Hildegard](https://attack.mitre.org/software/S0601) has started a monero service.(Citation: Unit 42 Hildegard Malware) [Unit 42 Hildegard Malware](https://unit42.paloaltonetworks.com/hildegard-malware-teamtnt/)
- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has created .service files using Systemd on victim Linux hosts to establish persistence.(Citation: Wiz Mini Shai-Hulud MAY 2026)(Citation: Hunt.io TeamPCP Toolkit MAY 2026)(Citation: Flashpoint Mini Shai-Hulud MAY 2026) [Flashpoint Mini Shai-Hulud MAY 2026](https://flashpoint.io/blog/mini-shai-hulud-worm-new-era-ci-cd-exploitation/) · [Hunt.io TeamPCP Toolkit MAY 2026](https://hunt.io/blog/teampcp-python-toolkit-firescale-github-c2-takedown) · [Wiz Mini Shai-Hulud MAY 2026](https://www.wiz.io/blog/mini-shai-hulud-strikes-again-tanstack-more-npm-packages-compromised)
- [S0192 - Pupy](../../../../Threat%20Intelligence/Software/Tools/S0192%20-%20Pupy.md) — [Pupy](https://attack.mitre.org/software/S0192) can be used to establish persistence using a systemd service.(Citation: GitHub Pupy) [GitHub Pupy](https://github.com/n1nj4sec/pupy)
- [S1222 - RIFLESPINE](../../../../Threat%20Intelligence/Software/Malware/S1222%20-%20RIFLESPINE.md) — [RIFLESPINE](https://attack.mitre.org/software/S1222) can create a systemd service file for execution.(Citation: Google Cloud Mandiant UNC3886 2024) [Google Cloud Mandiant UNC3886 2024](https://cloud.google.com/blog/topics/threat-intelligence/uncovering-unc3886-espionage-operations)
- [G0106 - Rocke](../../../../Threat%20Intelligence/Groups/G0106%20-%20Rocke.md) — [Rocke](https://attack.mitre.org/groups/G0106) has installed a systemd service script to maintain persistence.(Citation: Anomali Rocke March 2019) [Anomali Rocke March 2019](https://www.anomali.com/blog/rocke-evolves-its-arsenal-with-a-new-malware-family-written-in-golang)
- [S1078 - RotaJakiro](../../../../Threat%20Intelligence/Software/Malware/S1078%20-%20RotaJakiro.md) — Depending on the Linux distribution and when executing with root permissions, [RotaJakiro](https://attack.mitre.org/software/S1078) may install persistence using a `.service` file under the `/lib/systemd/system/` folder.(Citation: RotaJakiro 2021 netlab360 analysis) [RotaJakiro 2021 netlab360 analysis](https://blog.netlab.360.com/stealth_rotajakiro_backdoor_en/)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has run `SYSTEMD_UNIT_PATH="/lib/systemd/ system/teleport.service` to establish persistence for the Teleport remote access tool.(Citation: Mandiant VMware vSphere JUL 2025) [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has stopped `systemd-resolved` in order to manipulate DNS and firewalls.(Citation: Socket Shai-Hulud November 2025) [Socket Shai-Hulud November 2025](https://socket.dev/blog/shai-hulud-strikes-again-v2)
- [S0663 - SysUpdate](../../../../Threat%20Intelligence/Software/Malware/S0663%20-%20SysUpdate.md) — [SysUpdate](https://attack.mitre.org/software/S0663) can copy a script to the user owned `/usr/lib/systemd/system/` directory with a symlink mapped to a `root` owned directory, `/etc/ystem/system`, in the unit configuration file's `ExecStart` directive to establish persistence and elevate privileges.(Citation: Lunghi Iron Tiger Linux) [Lunghi Iron Tiger Linux](https://www.trendmicro.com/en_us/research/23/c/iron-tiger-sysupdate-adds-linux-targeting.html)
- [G1056 - TeamPCP](../../../../Threat%20Intelligence/Groups/G1056%20-%20TeamPCP.md) — [TeamPCP](https://attack.mitre.org/groups/G1056) has used the systemd user service for malware persistence in targeted environments.(Citation: Wiz TeamPCP KICS MAR 2026) [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action)
- [S9041 - TeamPCP Cloud Stealer](../../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can create a systemd unit to execute a python script for persistence.(Citation: Wiz Trivy Compromise MAR 2026)(Citation: Aqua Security Blog Trivy Compromise APR 2026)(Citation: Wiz TeamPCP KICS MAR 2026) [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know) · [Wiz Trivy Compromise MAR 2026](https://www.wiz.io/blog/trivy-compromised-teampcp-supply-chain-attack) · [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has established persistence through the creation of a cryptocurrency mining system service using <code>systemctl</code>.(Citation: Trend Micro TeamTNT)(Citation: Cisco Talos Intelligence Group) [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/) · [Trend Micro TeamTNT](https://documents.trendmicro.com/assets/white_papers/wp-tracking-the-activities-of-teamTNT.pdf)

## Mitigations

- [M1033 - Limit Software Installation](../../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Restrict software installation to trusted repositories only and be cautious of orphaned software packages.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — The creation and modification of systemd service unit files is generally reserved for administrators such as the Linux root user and other users with superuser privileges.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict read/write access to systemd unit files to only select privileged users who have a legitimate need to manage system services.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit user access to system utilities such as `systemctl` to only users who have a legitimate need.

## Sources

- [airwalk backdoor unix systems](http://www.ouah.org/backdoors.html)
- [Anomali Rocke March 2019](https://www.anomali.com/blog/rocke-evolves-its-arsenal-with-a-new-malware-family-written-in-golang)
- [freedesktop systemd.service](https://www.freedesktop.org/software/systemd/man/systemd.service.html)
- [Linux man-pages: systemd January 2014](http://man7.org/linux/man-pages/man1/systemd.1.html)
- [Pepe Berba Systemd 2022](https://pberba.github.io/security/2022/02/07/linux-threat-hunting-for-persistence-systemd-generators/)
- [Berba hunting linux systemd](https://pberba.github.io/security/2022/01/30/linux-threat-hunting-for-persistence-systemd-timers-cron/)
- [Rapid7 Service Persistence 22JUNE2016](https://www.rapid7.com/db/modules/exploit/linux/local/service_persistence)
- [Elastic Security Labs Linux Persistence 2024](https://www.elastic.co/security-labs/primer-on-persistence-mechanisms)
- [lambert systemd 2022](https://redcanary.com/blog/attck-t1501-understanding-systemd-service-persistence/)
