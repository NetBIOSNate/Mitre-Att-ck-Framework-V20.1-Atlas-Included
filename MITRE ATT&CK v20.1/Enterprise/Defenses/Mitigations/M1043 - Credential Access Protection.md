# M1043 - Credential Access Protection

[Enterprise](../../README.md) / [Mitigations](README.md)

Credential Access Protection focuses on implementing measures to prevent adversaries from obtaining credentials, such as passwords, hashes, tokens, or keys, that could be used for unauthorized access. This involves restricting access to credential storage mechanisms, hardening configurations to block credential dumping methods, and using monitoring tools to detect suspicious credential-related activity. This mitigation can be implemented through the following measures:

Restrict Access to Credential Storage:

- Use Case: Prevent adversaries from accessing the SAM (Security Account Manager) database on Windows systems.
- Implementation: Enforce least privilege principles and restrict administrative access to credential stores such as `C:\Windows\System32\config\SAM`.

Use Credential Guard:

- Use Case: Isolate LSASS (Local Security Authority Subsystem Service) memory to prevent credential dumping.
- Implementation: Enable Windows Defender Credential Guard on enterprise endpoints to isolate secrets and protect them from unauthorized access.

Monitor for Credential Dumping Tools:

- Use Case: Detect and block known tools like Mimikatz or Windows Credential Editor.
- Implementation: Flag suspicious process behavior related to credential dumping.

Disable Cached Credentials:

- Use Case: Prevent adversaries from exploiting cached credentials on endpoints.
- Implementation: Configure group policy to reduce or eliminate the use of cached credentials (e.g., set Interactive logon: Number of previous logons to cache to 0).

Enable Secure Boot and Memory Protections:

- Use Case: Prevent memory-based attacks used to extract credentials.
- Implementation: Configure Secure Boot and enforce hardware-based security features like DEP (Data Execution Prevention) and ASLR (Address Space Layout Randomization).

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1043)

## Mitigated techniques

- [T1558.005 - Ccache Files](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.005%20-%20Ccache%20Files/README.md)
- [T1601.002 - Downgrade System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.002%20-%20Downgrade%20System%20Image/README.md)
- [T1547.008 - LSASS Driver](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.008%20-%20LSASS%20Driver/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1601 - Modify System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/README.md)
- [T1599.001 - Network Address Translation Traversal](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/T1599.001%20-%20Network%20Address%20Translation%20Traversal/README.md)
- [T1599 - Network Boundary Bridging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/README.md)
- [T1003 - OS Credential Dumping](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/README.md)
- [T1601.001 - Patch System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.001%20-%20Patch%20System%20Image/README.md)
- [T1558 - Steal or Forge Kerberos Tickets](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/README.md)
