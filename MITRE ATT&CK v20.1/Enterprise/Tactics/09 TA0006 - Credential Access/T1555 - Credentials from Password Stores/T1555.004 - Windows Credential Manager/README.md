# T1555.004 - Windows Credential Manager

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1555 - Credentials from Password Stores](../README.md)

Adversaries may acquire credentials from the Windows Credential Manager. The Credential Manager stores credentials for signing into websites, applications, and/or devices that request authentication through NTLM or Kerberos in Credential Lockers (previously known as Windows Vaults).(Citation: Microsoft Credential Manager store)(Citation: Microsoft Credential Locker)

The Windows Credential Manager separates website credentials from application or network credentials in two lockers. As part of [Credentials from Web Browsers](https://attack.mitre.org/techniques/T1555/003), Internet Explorer and Microsoft Edge website credentials are managed by the Credential Manager and are stored in the Web Credentials locker. Application and network credentials are stored in the Windows Credentials locker.

Credential Lockers store credentials in encrypted `.vcrd` files, located under `%Systemdrive%\Users\\[Username]\AppData\Local\Microsoft\\[Vault/Credentials]\`. The encryption key can be found in a file named <code>Policy.vpol</code>, typically located in the same folder as the credentials.(Citation: passcape Windows Vault)(Citation: Malwarebytes The Windows Vault)

Adversaries may list credentials managed by the Windows Credential Manager through several mechanisms. <code>vaultcmd.exe</code> is a native Windows executable that can be used to enumerate credentials stored in the Credential Locker through a command-line interface. Adversaries may also gather credentials by directly reading files located inside of the Credential Lockers. Windows APIs, such as <code>CredEnumerateA</code>, may also be abused to list credentials managed by the Credential Manager.(Citation: Microsoft CredEnumerate)(Citation: Delpy Mimikatz Crendential Manager)

Adversaries may also obtain credentials from credential backups. Credential backups and restorations may be performed by running <code>rundll32.exe keymgr.dll KRShowKeyMgr</code> then selecting the “Back up...” button on the “Stored User Names and Passwords” GUI.

Password recovery tools may also obtain plain text passwords from the Credential Manager.(Citation: Malwarebytes The Windows Vault)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1555/004)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0044 - Juicy Mix](../../../../Threat%20Intelligence/Campaigns/C0044%20-%20Juicy%20Mix.md) — During [Juicy Mix](https://attack.mitre.org/campaigns/C0044), [OilRig](https://attack.mitre.org/groups/G0049) used a Windows Credential Manager stealer for credential access.(Citation: ESET OilRig Campaigns Sep 2023) [ESET OilRig Campaigns Sep 2023](https://www.welivesecurity.com/en/eset-research/oilrigs-outer-space-juicy-mix-same-ol-rig-new-drill-pipes/)
- [S0526 - KGH_SPY](../../../../Threat%20Intelligence/Software/Malware/S0526%20-%20KGH_SPY.md) — [KGH_SPY](https://attack.mitre.org/software/S0526) can collect credentials from the Windows Credential Manager.(Citation: Cybereason Kimsuky November 2020) [Cybereason Kimsuky November 2020](https://www.cybereason.com/blog/back-to-the-future-inside-the-kimsuky-kgh-spyware-suite)
- [S0349 - LaZagne](../../../../Threat%20Intelligence/Software/Tools/S0349%20-%20LaZagne.md) — [LaZagne](https://attack.mitre.org/software/S0349) can obtain credentials from Vault files.(Citation: GitHub LaZagne Dec 2018) [GitHub LaZagne Dec 2018](https://github.com/AlessandroZ/LaZagne)
- [S0681 - Lizar](../../../../Threat%20Intelligence/Software/Malware/S0681%20-%20Lizar.md) — [Lizar](https://attack.mitre.org/software/S0681) has a plugin that can retrieve credentials from Internet Explorer and Microsoft Edge using `vaultcmd.exe` and another that can collect RDP access credentials using the `CredEnumerateW` function.(Citation: BiZone Lizar May 2021) [BiZone Lizar May 2021](https://bi-zone.medium.com/from-pentest-to-apt-attack-cybercriminal-group-fin7-disguises-its-malware-as-an-ethical-hackers-c23c9a75e319)
- [S0002 - Mimikatz](../../../../Threat%20Intelligence/Software/Tools/S0002%20-%20Mimikatz.md) — [Mimikatz](https://attack.mitre.org/software/S0002) contains functionality to acquire credentials from the Windows Credential Manager.(Citation: Delpy Mimikatz Crendential Manager) [Delpy Mimikatz Crendential Manager](https://github.com/gentilkiwi/mimikatz/wiki/howto-~-credential-manager-saved-credentials)
- [G0049 - OilRig](../../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has used credential dumping tool named VALUEVAULT to steal credentials from the Windows Credential Manager.(Citation: FireEye APT34 July 2019) [FireEye APT34 July 2019](https://www.fireeye.com/blog/threat-research/2019/07/hard-pass-declining-apt34-invite-to-join-their-professional-network.html)
- [S0194 - PowerSploit](../../../../Threat%20Intelligence/Software/Tools/S0194%20-%20PowerSploit.md) — [PowerSploit](https://attack.mitre.org/software/S0194) contains a collection of Exfiltration modules that can harvest credentials from Windows vault credential objects.(Citation: GitHub PowerSploit May 2012)(Citation: PowerSploit Documentation) [GitHub PowerSploit May 2012](https://github.com/PowerShellMafia/PowerSploit) · [PowerSploit Documentation](http://powersploit.readthedocs.io)
- [S0629 - RainyDay](../../../../Threat%20Intelligence/Software/Malware/S0629%20-%20RainyDay.md) — [RainyDay](https://attack.mitre.org/software/S0629) can use the QuarksPwDump tool to obtain local passwords and domain cached credentials.(Citation: Bitdefender Naikon April 2021) [Bitdefender Naikon April 2021](https://www.bitdefender.com/files/News/CaseStudies/study/396/Bitdefender-PR-Whitepaper-NAIKON-creat5397-en-EN.pdf)
- [S0240 - ROKRAT](../../../../Threat%20Intelligence/Software/Malware/S0240%20-%20ROKRAT.md) — [ROKRAT](https://attack.mitre.org/software/S0240) can steal credentials by leveraging the Windows Vault mechanism.(Citation: Talos Group123) [Talos Group123](https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html)
- [S0692 - SILENTTRINITY](../../../../Threat%20Intelligence/Software/Tools/S0692%20-%20SILENTTRINITY.md) — [SILENTTRINITY](https://attack.mitre.org/software/S0692) can gather Windows Vault credentials.(Citation: GitHub SILENTTRINITY Modules July 2019) [GitHub SILENTTRINITY Modules July 2019](https://github.com/byt3bl33d3r/SILENTTRINITY/tree/master/silenttrinity/core/teamserver/modules/boo)
- [G0038 - Stealth Falcon](../../../../Threat%20Intelligence/Groups/G0038%20-%20Stealth%20Falcon.md) — [Stealth Falcon](https://attack.mitre.org/groups/G0038) malware gathers passwords from the Windows Credential Vault.(Citation: Citizen Lab Stealth Falcon May 2016) [Citizen Lab Stealth Falcon May 2016](https://citizenlab.org/2016/05/stealth-falcon/)
- [G0010 - Turla](../../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) has gathered credentials from the Windows Credential Manager tool.(Citation: Symantec Waterbug Jun 2019) [Symantec Waterbug Jun 2019](https://www.symantec.com/blogs/threat-intelligence/waterbug-espionage-governments)
- [S0476 - Valak](../../../../Threat%20Intelligence/Software/Malware/S0476%20-%20Valak.md) — [Valak](https://attack.mitre.org/software/S0476) can use a .NET compiled module named exchgrabber to enumerate credentials from the Credential Manager.(Citation: SentinelOne Valak June 2020) [SentinelOne Valak June 2020](https://assets.sentinelone.com/labs/sentinel-one-valak-i)
- [G0102 - Wizard Spider](../../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has used PowerShell cmdlet `Invoke-WCMDump` to enumerate Windows credentials in the Credential Manager in a compromised network.(Citation: Mandiant FIN12 Oct 2021) [Mandiant FIN12 Oct 2021](https://web.archive.org/web/20220313061955/https://www.mandiant.com/sites/default/files/2021-10/fin12-group-profile.pdf)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider enabling the “Network access: Do not allow storage of passwords and credentials for network authentication” setting that will prevent network credentials from being stored by the Credential Manager.(Citation: Microsoft Network access Credential Manager) [Microsoft Network access Credential Manager](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj852185%28v=ws.11%29?redirectedfrom=MSDN)

## Detection strategies

- [DET0134 - Detect Suspicious Access to Windows Credential Manager](../../../../Defenses/Detection%20Strategies/DET0134%20-%20Detect%20Suspicious%20Access%20to%20Windows%20Credential%20Manager.md)

## Sources

- [Malwarebytes The Windows Vault](https://blog.malwarebytes.com/101/2016/01/the-windows-vaults/)
- [Delpy Mimikatz Crendential Manager](https://github.com/gentilkiwi/mimikatz/wiki/howto-~-credential-manager-saved-credentials)
- [Microsoft Credential Locker](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-8.1-and-8/jj554668%28v=ws.11%29?redirectedfrom=MSDN)
- [Microsoft Credential Manager store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh994565%28v=ws.11%29#credential-manager-store)
- [Microsoft CredEnumerate](https://docs.microsoft.com/en-us/windows/win32/api/wincred/nf-wincred-credenumeratea)
- [passcape Windows Vault](https://www.passcape.com/windows_password_recovery_vault_explorer)
