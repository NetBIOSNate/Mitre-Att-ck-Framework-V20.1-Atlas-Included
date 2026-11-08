# T1056 - Input Capture

[Enterprise](../../../README.md) / [Collection](../README.md)

Adversaries may use methods of capturing user input to obtain credentials or collect information. During normal system usage, users often provide credentials to various different locations, such as login pages/portals or system dialog boxes. Input capture mechanisms may be transparent to the user (e.g. [Credential API Hooking](https://attack.mitre.org/techniques/T1056/004)) or rely on deceiving the user into providing input into what they believe to be a genuine service (e.g. [Web Portal Capture](https://attack.mitre.org/techniques/T1056/003)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1056)

**Tactics**  [Credential Access](../../09%20TA0006%20-%20Credential%20Access/README.md), [Collection](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1056.004 - Credential API Hooking](T1056.004%20-%20Credential%20API%20Hooking/README.md)
- [T1056.002 - GUI Input Capture](T1056.002%20-%20GUI%20Input%20Capture/README.md)
- [T1056.001 - Keylogging](T1056.001%20-%20Keylogging/README.md)
- [T1056.003 - Web Portal Capture](T1056.003%20-%20Web%20Portal%20Capture/README.md)

## Procedure examples

- [G0087 - APT39](../../../Threat%20Intelligence/Groups/G0087%20-%20APT39.md) — [APT39](https://attack.mitre.org/groups/G0087) has utilized tools to capture mouse movements.(Citation: FBI FLASH APT39 September 2020) [FBI FLASH APT39 September 2020](https://www.iranwatch.org/sites/default/files/public-intelligence-alert.pdf)
- [G1044 - APT42](../../../Threat%20Intelligence/Groups/G1044%20-%20APT42.md) — [APT42](https://attack.mitre.org/groups/G1044) has used credential harvesting websites.(Citation: Mandiant APT42-untangling) [Mandiant APT42-untangling](https://cloud.google.com/blog/topics/threat-intelligence/untangling-iran-apt42-operations)
- [S0631 - Chaes](../../../Threat%20Intelligence/Software/Malware/S0631%20-%20Chaes.md) — [Chaes](https://attack.mitre.org/software/S0631) has a module to perform any API hooking it desires.(Citation: Cybereason Chaes Nov 2020) [Cybereason Chaes Nov 2020](https://www.cybereason.com/hubfs/dam/collateral/reports/11-2020-Chaes-e-commerce-malware-research.pdf)
- [S0381 - FlawedAmmyy](../../../Threat%20Intelligence/Software/Malware/S0381%20-%20FlawedAmmyy.md) — [FlawedAmmyy](https://attack.mitre.org/software/S0381) can collect mouse events.(Citation: Korean FSI TA505 2020) [Korean FSI TA505 2020](https://www.fsec.or.kr/user/bbs/fsec/163/344/bbsDataView/1382.do?page=1&column=&search=&searchSDate=&searchEDate=&bbsDataCategory=)
- [S1245 - InvisibleFerret](../../../Threat%20Intelligence/Software/Malware/S1245%20-%20InvisibleFerret.md) — [InvisibleFerret](https://attack.mitre.org/software/S1245) has collected mouse and keyboard events using “pyWinhook”.(Citation: PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023) [PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023](https://unit42.paloaltonetworks.com/two-campaigns-by-north-korea-bad-actors-target-job-hunters/)
- [S0641 - Kobalos](../../../Threat%20Intelligence/Software/Malware/S0641%20-%20Kobalos.md) — [Kobalos](https://attack.mitre.org/software/S0641) has used a compromised SSH client to capture the hostname, port, username and password used to establish an SSH connection from the compromised host.(Citation: ESET Kobalos Feb 2021)(Citation: ESET Kobalos Jan 2021) [ESET Kobalos Feb 2021](https://www.welivesecurity.com/2021/02/02/kobalos-complex-linux-threat-high-performance-computing-infrastructure/) · [ESET Kobalos Jan 2021](https://www.welivesecurity.com/wp-content/uploads/2021/01/ESET_Kobalos.pdf)
- [C0049 - Leviathan Australian Intrusions](../../../Threat%20Intelligence/Campaigns/C0049%20-%20Leviathan%20Australian%20Intrusions.md) — [Leviathan](https://attack.mitre.org/groups/G0065) captured submitted multfactor authentication codes and other technical artifacts related to remote access sessions during [Leviathan Australian Intrusions](https://attack.mitre.org/campaigns/C0049).(Citation: CISA Leviathan 2024) [CISA Leviathan 2024](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-190a)
- [S1060 - Mafalda](../../../Threat%20Intelligence/Software/Malware/S1060%20-%20Mafalda.md) — [Mafalda](https://attack.mitre.org/software/S1060) can conduct mouse event logging.(Citation: SentinelLabs Metador Technical Appendix Sept 2022) [SentinelLabs Metador Technical Appendix Sept 2022](https://docs.google.com/document/d/1e9ZTW9b71YwFWS_18ZwDAxa-cYbV8q1wUefmKZLYVsA/edit#heading=h.lmnbtht1ikzm)
- [S1059 - metaMain](../../../Threat%20Intelligence/Software/Malware/S1059%20-%20metaMain.md) — [metaMain](https://attack.mitre.org/software/S1059) can log mouse events.(Citation: SentinelLabs Metador Technical Appendix Sept 2022) [SentinelLabs Metador Technical Appendix Sept 2022](https://docs.google.com/document/d/1e9ZTW9b71YwFWS_18ZwDAxa-cYbV8q1wUefmKZLYVsA/edit#heading=h.lmnbtht1ikzm)
- [S1131 - NPPSPY](../../../Threat%20Intelligence/Software/Tools/S1131%20-%20NPPSPY.md) — [NPPSPY](https://attack.mitre.org/software/S1131) captures user input into the Winlogon process by redirecting RPC traffic from legitimate listening DLLs within the operating system to a newly registered malicious item that allows for recording logon information in cleartext.(Citation: Huntress NPPSPY 2022) [Huntress NPPSPY 2022](https://www.huntress.com/blog/cleartext-shenanigans-gifting-user-passwords-to-adversaries-with-nppspy)
- [G1046 - Storm-1811](../../../Threat%20Intelligence/Groups/G1046%20-%20Storm-1811.md) — [Storm-1811](https://attack.mitre.org/groups/G1046) has used a PowerShell script to capture user credentials after prompting a user to authenticate to run a malicious script masquerading as a legitimate update item.(Citation: rapid7-email-bombing) [rapid7-email-bombing](https://www.rapid7.com/blog/post/2024/05/10/ongoing-social-engineering-campaign-linked-to-black-basta-ransomware-operators)
- [C0039 - Versa Director Zero Day Exploitation](../../../Threat%20Intelligence/Campaigns/C0039%20-%20Versa%20Director%20Zero%20Day%20Exploitation.md) — [Versa Director Zero Day Exploitation](https://attack.mitre.org/campaigns/C0039) intercepted and harvested credentials from user logins to compromised devices.(Citation: Lumen Versa 2024) [Lumen Versa 2024](https://www.lumen.com/blog/en-us/uncovering-versa-director-zero-day-exploitation)

## Detection strategies

- [DET0102 - Behavioral Detection of Input Capture Across Platforms](../../../Defenses/Detection%20Strategies/DET0102%20-%20Behavioral%20Detection%20of%20Input%20Capture%20Across%20Platforms.md)

## Sources

- [Adventures of a Keystroke](http://opensecuritytraining.info/Keylogging_files/The%20Adventures%20of%20a%20Keystroke.pdf)
