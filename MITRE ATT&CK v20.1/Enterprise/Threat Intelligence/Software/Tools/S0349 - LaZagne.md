# S0349 - LaZagne

[Enterprise](../../../README.md) / [Tools](README.md)

[LaZagne](https://attack.mitre.org/software/S0349) is a post-exploitation, open-source tool used to recover stored passwords on a system. It has modules for Windows, Linux, and OSX, but is mainly focused on Windows systems. [LaZagne](https://attack.mitre.org/software/S0349) is publicly available on GitHub.(Citation: GitHub LaZagne Dec 2018)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0349)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Used by

- [G1024 - Akira](../../Groups/G1024%20-%20Akira.md)
- [G0022 - APT3](../../Groups/G0022%20-%20APT3.md)
- [G0064 - APT33](../../Groups/G0064%20-%20APT33.md)
- [G0120 - Evilnum](../../Groups/G0120%20-%20Evilnum.md)
- [G0100 - Inception](../../Groups/G0100%20-%20Inception.md)
- [G0077 - Leafminer](../../Groups/G0077%20-%20Leafminer.md)
- [G0069 - MuddyWater](../../Groups/G0069%20-%20MuddyWater.md)
- [G0049 - OilRig](../../Groups/G0049%20-%20OilRig.md)
- [G1015 - Scattered Spider](../../Groups/G1015%20-%20Scattered%20Spider.md)
- [G0139 - TeamTNT](../../Groups/G0139%20-%20TeamTNT.md)
- [G0131 - Tonto Team](../../Groups/G0131%20-%20Tonto%20Team.md)
- [G0102 - Wizard Spider](../../Groups/G0102%20-%20Wizard%20Spider.md)

## Techniques used

- [T1003.008 - /etc/passwd and /etc/shadow](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.008%20-%20etc%20-%20passwd%20and%20-%20etc%20-%20shadow/README.md)
- [T1003.005 - Cached Domain Credentials](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.005%20-%20Cached%20Domain%20Credentials/README.md)
- [T1555 - Credentials from Password Stores](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/README.md)
- [T1555.003 - Credentials from Web Browsers](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.003%20-%20Credentials%20from%20Web%20Browsers/README.md)
- [T1552.001 - Credentials In Files](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1555.001 - Keychain](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.001%20-%20Keychain/README.md)
- [T1003.004 - LSA Secrets](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.004%20-%20LSA%20Secrets/README.md)
- [T1003.001 - LSASS Memory](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1003.007 - Proc Filesystem](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.007%20-%20Proc%20Filesystem/README.md)
- [T1555.004 - Windows Credential Manager](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.004%20-%20Windows%20Credential%20Manager/README.md)

## Sources

- [GitHub LaZagne Dec 2018](https://github.com/AlessandroZ/LaZagne)
