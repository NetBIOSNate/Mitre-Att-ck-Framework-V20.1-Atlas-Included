# T1552.006 - Group Policy Preferences

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1552 - Unsecured Credentials](../README.md)

Adversaries may attempt to find unsecured credentials in Group Policy Preferences (GPP). GPP are tools that allow administrators to create domain policies with embedded credentials. These policies allow administrators to set local accounts.(Citation: Microsoft GPP 2016)

These group policies are stored in SYSVOL on a domain controller. This means that any domain user can view the SYSVOL share and decrypt the password (using the AES key that has been made public).(Citation: Microsoft GPP Key)

The following tools and scripts can be used to gather and decrypt the password file from Group Policy Preference XML files:

* Metasploit’s post exploitation module: <code>post/windows/gather/credentials/gpp</code>
* Get-GPPPassword(Citation: Obscuresecurity Get-GPPPassword)
* gpprefdecrypt.py

On the SYSVOL share, adversaries may use the following command to enumerate potential GPP XML files: <code>dir /s * .xml</code>

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1552/006)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0064 - APT33](../../../../Threat%20Intelligence/Groups/G0064%20-%20APT33.md) — [APT33](https://attack.mitre.org/groups/G0064) has used a variety of publicly available tools like Gpppassword to gather credentials.(Citation: Symantec Elfin Mar 2019)(Citation: FireEye APT33 Guardrail) [Symantec Elfin Mar 2019](https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage) · [FireEye APT33 Guardrail](https://www.fireeye.com/blog/threat-research/2018/12/overruled-containing-a-potentially-destructive-adversary.html)
- [S9022 - MirrorStealer](../../../../Threat%20Intelligence/Software/Malware/S9022%20-%20MirrorStealer.md) — [MirrorStealer](https://attack.mitre.org/software/S9022) can target Group Policy Preferences for credentials.(Citation: Trend Micro Earth Kasha NOV 2024) [Trend Micro Earth Kasha NOV 2024](https://www.trendmicro.com/en_us/research/24/k/lodeinfo-campaign-of-earth-kasha.html)
- [S0194 - PowerSploit](../../../../Threat%20Intelligence/Software/Tools/S0194%20-%20PowerSploit.md) — [PowerSploit](https://attack.mitre.org/software/S0194) contains a collection of Exfiltration modules that can harvest credentials from Group Policy Preferences.(Citation: GitHub PowerSploit May 2012)(Citation: PowerSploit Documentation) [GitHub PowerSploit May 2012](https://github.com/PowerShellMafia/PowerSploit) · [PowerSploit Documentation](http://powersploit.readthedocs.io)
- [S0692 - SILENTTRINITY](../../../../Threat%20Intelligence/Software/Tools/S0692%20-%20SILENTTRINITY.md) — [SILENTTRINITY](https://attack.mitre.org/software/S0692) has a module that can extract cached GPP passwords.(Citation: GitHub SILENTTRINITY Modules July 2019) [GitHub SILENTTRINITY Modules July 2019](https://github.com/byt3bl33d3r/SILENTTRINITY/tree/master/silenttrinity/core/teamserver/modules/boo)
- [G0102 - Wizard Spider](../../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has used PowerShell cmdlets `Get-GPPPassword` and `Find-GPOPassword` to find unsecured credentials in a compromised network group policy.(Citation: Mandiant FIN12 Oct 2021) [Mandiant FIN12 Oct 2021](https://web.archive.org/web/20220313061955/https://www.mandiant.com/sites/default/files/2021-10/fin12-group-profile.pdf)

## Mitigations

- [M1015 - Active Directory Configuration](../../../../Defenses/Mitigations/M1015%20-%20Active%20Directory%20Configuration.md) — Remove vulnerable Group Policy Preferences.(Citation: Microsoft MS14-025) [Microsoft MS14-025](http://support.microsoft.com/kb/2962486)
- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Search SYSVOL for any existing GGPs that may contain credentials and remove them.(Citation: ADSecurity Finding Passwords in SYSVOL) [ADSecurity Finding Passwords in SYSVOL](https://adsecurity.org/?p=2288)
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Apply patch KB2962486 which prevents credentials from being stored in GPPs.(Citation: ADSecurity Finding Passwords in SYSVOL)(Citation: MS14-025) [ADSecurity Finding Passwords in SYSVOL](https://adsecurity.org/?p=2288) · [MS14-025](https://support.microsoft.com/en-us/help/2962486/ms14-025-vulnerability-in-group-policy-preferences-could-allow-elevati)

## Detection strategies

- [DET0381 - Detect Access and Decryption of Group Policy Preference (GPP) Credentials in SYSVOL](../../../../Defenses/Detection%20Strategies/DET0381%20-%20Detect%20Access%20and%20Decryption%20of%20Group%20Policy%20Preference%20%28GPP%29%20Credentials%20in%20SYSVOL.md)

## Sources

- [Obscuresecurity Get-GPPPassword](https://obscuresecurity.blogspot.co.uk/2012/05/gpp-password-retrieval-with-powershell.html)
- [Microsoft GPP 2016](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn581922%28v%3Dws.11%29)
- [Microsoft GPP Key](https://msdn.microsoft.com/library/cc422924.aspx)
- [ADSecurity Finding Passwords in SYSVOL](https://adsecurity.org/?p=2288)
