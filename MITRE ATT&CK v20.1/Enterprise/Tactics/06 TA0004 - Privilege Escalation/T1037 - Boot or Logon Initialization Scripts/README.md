# T1037 - Boot or Logon Initialization Scripts

[Enterprise](../../../README.md) / [Privilege Escalation](../README.md)

Adversaries may use scripts automatically executed at boot or logon initialization to establish persistence.(Citation: Mandiant APT29 Eye Spy Email Nov 22)(Citation: Anomali Rocke March 2019) Initialization scripts can be used to perform administrative functions, which may often execute other programs or send information to an internal logging server. These scripts can vary based on operating system and whether applied locally or remotely.  

Adversaries may use these scripts to maintain persistence on a single system. Depending on the access configuration of the logon scripts, either local credentials or an administrator account may be necessary. 

An adversary may also be able to escalate their privileges since some boot or logon initialization scripts run with higher privileges.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1037)

**Tactics**  [Persistence](../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1037.002 - Login Hook](T1037.002%20-%20Login%20Hook/README.md)
- [T1037.001 - Logon Script (Windows)](T1037.001%20-%20Logon%20Script%20%28Windows%29/README.md)
- [T1037.003 - Network Logon Script](T1037.003%20-%20Network%20Logon%20Script/README.md)
- [T1037.004 - RC Scripts](T1037.004%20-%20RC%20Scripts/README.md)
- [T1037.005 - Startup Items](T1037.005%20-%20Startup%20Items/README.md)

## Procedure examples

- [G0016 - APT29](../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has hijacked legitimate application-specific startup scripts to enable malware to execute on system startup.(Citation: Mandiant APT29 Eye Spy Email Nov 22) [Mandiant APT29 Eye Spy Email Nov 22](https://www.mandiant.com/resources/blog/unc3524-eye-spy-email)
- [G0096 - APT41](../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) used a hidden shell script in `/etc/rc.d/init.d` to leverage the `ADORE.XSEC`backdoor and `Adore-NG` rootkit.(Citation: apt41_mandiant) [apt41_mandiant](https://www.mandiant.com/sites/default/files/2022-02/rt-apt41-dual-operation.pdf)
- [C0046 - ArcaneDoor](../../../Threat%20Intelligence/Campaigns/C0046%20-%20ArcaneDoor.md) — [ArcaneDoor](https://attack.mitre.org/campaigns/C0046) used malicious boot scripts to install the [Line Runner](https://attack.mitre.org/software/S1188) backdoor on victim devices.(Citation: Cisco ArcaneDoor 2024) [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [G0106 - Rocke](../../../Threat%20Intelligence/Groups/G0106%20-%20Rocke.md) — [Rocke](https://attack.mitre.org/groups/G0106) has installed an "init.d" startup script to maintain persistence.(Citation: Anomali Rocke March 2019) [Anomali Rocke March 2019](https://www.anomali.com/blog/rocke-evolves-its-arsenal-with-a-new-malware-family-written-in-golang)
- [S1078 - RotaJakiro](../../../Threat%20Intelligence/Software/Malware/S1078%20-%20RotaJakiro.md) — Depending on the Linux distribution and when executing with root permissions, [RotaJakiro](https://attack.mitre.org/software/S1078) may install persistence using a `.conf` file in the `/etc/init/` folder.(Citation: RotaJakiro 2021 netlab360 analysis) [RotaJakiro 2021 netlab360 analysis](https://blog.netlab.360.com/stealth_rotajakiro_backdoor_en/)
- [S9024 - SPAWNCHIMERA](../../../Threat%20Intelligence/Software/Malware/S9024%20-%20SPAWNCHIMERA.md) — [SPAWNCHIMERA](https://attack.mitre.org/software/S9024) has modified the boot process files within `/tmp/coreboot_fs/bin/init` to establish persistence.(Citation: CISA SPAWNCHIMERA RESURGE February 2026) [CISA SPAWNCHIMERA RESURGE February 2026](https://www.cisa.gov/news-events/analysis-reports/ar25-087a)
- [G1048 - UNC3886](../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has attempted to bypass digital signature verification checks at startup by adding a command to the startup config `/etc/init.d/localnet` within the rootfs.gz archive of both FortiManager and FortiAnalyzer devices.(Citation: Mandiant Fortinet Zero Day) [Mandiant Fortinet Zero Day](https://www.mandiant.com/resources/blog/fortinet-malware-ecosystem)
- [S1217 - VIRTUALPITA](../../../Threat%20Intelligence/Software/Malware/S1217%20-%20VIRTUALPITA.md) — [VIRTUALPITA](https://attack.mitre.org/software/S1217) can persist as an init.d startup service on Linux vCenter systems.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict write access to logon scripts to specific administrators.
- [M1024 - Restrict Registry Permissions](../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Ensure proper permissions are set for Registry hives to prevent users from modifying keys for logon scripts that may lead to persistence.

## Detection strategies

- [DET0112 - Boot or Logon Initialization Scripts Detection Strategy](../../../Defenses/Detection%20Strategies/DET0112%20-%20Boot%20or%20Logon%20Initialization%20Scripts%20Detection%20Strategy.md)

## Sources

- [Anomali Rocke March 2019](https://www.anomali.com/blog/rocke-evolves-its-arsenal-with-a-new-malware-family-written-in-golang)
- [Mandiant APT29 Eye Spy Email Nov 22](https://www.mandiant.com/resources/blog/unc3524-eye-spy-email)
