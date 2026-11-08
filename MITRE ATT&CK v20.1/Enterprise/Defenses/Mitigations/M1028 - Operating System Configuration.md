# M1028 - Operating System Configuration

[Enterprise](../../README.md) / [Mitigations](README.md)

Operating System Configuration involves adjusting system settings and hardening the default configurations of an operating system (OS) to mitigate adversary exploitation and prevent abuse of system functionality. Proper OS configurations address security vulnerabilities, limit attack surfaces, and ensure robust defense against a wide range of techniques. This mitigation can be implemented through the following measures: 

Disable Unused Features:

- Turn off SMBv1, LLMNR, and NetBIOS where not needed.
- Disable remote registry and unnecessary services.

Enforce OS-level Protections:

- Enable Data Execution Prevention (DEP), Address Space Layout Randomization (ASLR), and Control Flow Guard (CFG) on Windows.
- Use AppArmor or SELinux on Linux for mandatory access controls.

Secure Access Settings:

- Enable User Account Control (UAC) for Windows.
- Restrict root/sudo access on Linux/macOS and enforce strong permissions using sudoers files.

File System Hardening:

- Implement least-privilege access for critical files and system directories.
- Audit permissions regularly using tools like icacls (Windows) or getfacl/chmod (Linux/macOS).

Secure Remote Access:

- Restrict RDP, SSH, and VNC to authorized IPs using firewall rules.
- Enable NLA for RDP and enforce strong password/lockout policies.

Harden Boot Configurations:

- Enable Secure Boot and enforce UEFI/BIOS password protection.
- Use BitLocker or LUKS to encrypt boot drives.

Regular Audits:

- Periodically audit OS configurations using tools like CIS Benchmarks or SCAP tools.

*Tools for Implementation*

Windows:

- Microsoft Group Policy Objects (GPO): Centrally enforce OS security settings.
- Windows Defender Exploit Guard: Built-in OS protection against exploits.
- CIS-CAT Pro: Audit Windows security configurations based on CIS Benchmarks.

Linux/macOS:

- AppArmor/SELinux: Enforce mandatory access controls.
- Lynis: Perform comprehensive security audits.
- SCAP Security Guide: Automate configuration hardening using Security Content Automation Protocol.

Cross-Platform:

- Ansible or Chef/Puppet: Automate configuration hardening at scale.
- OpenSCAP: Perform compliance and configuration checks.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1028)

## Mitigated techniques

- [T1548 - Abuse Elevation Control Mechanism](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1546.008 - Accessibility Features](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.008%20-%20Accessibility%20Features/README.md)
- [T1087 - Account Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/README.md)
- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1053.002 - At](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.002%20-%20At/README.md)
- [T1197 - BITS Jobs](../../Tactics/04%20TA0002%20-%20Execution/T1197%20-%20BITS%20Jobs/README.md)
- [T1003.005 - Cached Domain Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.005%20-%20Cached%20Domain%20Credentials/README.md)
- [T1092 - Communication Through Removable Media](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1092%20-%20Communication%20Through%20Removable%20Media/README.md)
- [T1136 - Create Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1087.002 - Domain Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.002%20-%20Domain%20Account/README.md)
- [T1136.002 - Domain Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.002%20-%20Domain%20Account/README.md)
- [T1036.007 - Double File Extension](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.007%20-%20Double%20File%20Extension/README.md)
- [T1574.006 - Dynamic Linker Hijacking](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.006%20-%20Dynamic%20Linker%20Hijacking/README.md)
- [T1011.001 - Exfiltration Over Bluetooth](../../Tactics/14%20TA0010%20-%20Exfiltration/T1011%20-%20Exfiltration%20Over%20Other%20Network%20Medium/T1011.001%20-%20Exfiltration%20Over%20Bluetooth/README.md)
- [T1011 - Exfiltration Over Other Network Medium](../../Tactics/14%20TA0010%20-%20Exfiltration/T1011%20-%20Exfiltration%20Over%20Other%20Network%20Medium/README.md)
- [T1564.002 - Hidden Users](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.002%20-%20Hidden%20Users/README.md)
- [T1490 - Inhibit System Recovery](../../Tactics/15%20TA0040%20-%20Impact/T1490%20-%20Inhibit%20System%20Recovery/README.md)
- [T1553.004 - Install Root Certificate](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.004%20-%20Install%20Root%20Certificate/README.md)
- [T1087.001 - Local Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.001%20-%20Local%20Account/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1556 - Modify Authentication Process](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/README.md)
- [T1556.008 - Network Provider DLL](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.008%20-%20Network%20Provider%20DLL/README.md)
- [T1135 - Network Share Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1135%20-%20Network%20Share%20Discovery/README.md)
- [T1003 - OS Credential Dumping](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/README.md)
- [T1556.002 - Password Filter DLL](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.002%20-%20Password%20Filter%20DLL/README.md)
- [T1690 - Prevent Command History Logging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1690%20-%20Prevent%20Command%20History%20Logging/README.md)
- [T1563.002 - RDP Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.002%20-%20RDP%20Hijacking/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1053 - Scheduled Task/Job](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/README.md)
- [T1003.002 - Security Account Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1548.001 - Setuid and Setgid](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.001%20-%20Setuid%20and%20Setgid/README.md)
- [T1552.003 - Shell History](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.003%20-%20Shell%20History/README.md)
- [T1553 - Subvert Trust Controls](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/README.md)
- [T1548.003 - Sudo and Sudo Caching](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.003%20-%20Sudo%20and%20Sudo%20Caching/README.md)
- [T1542.005 - TFTP Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.005%20-%20TFTP%20Boot/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)
