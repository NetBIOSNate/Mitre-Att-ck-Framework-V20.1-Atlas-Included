# S1131 - NPPSPY

[Enterprise](../../../README.md) / [Tools](README.md)

NPPSPY is an implementation of a theoretical mechanism first presented in 2004 for capturing credentials submitted to a Windows system via a rogue Network Provider API item. NPPSPY captures credentials following submission and writes them to a file on the victim system for follow-on exfiltration.(Citation: Huntress NPPSPY 2022)(Citation: Polak NPPSPY 2004)

[MITRE ATT&CK record](https://attack.mitre.org/software/S1131)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1557 - Adversary-in-the-Middle](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/README.md)
- [T1119 - Automated Collection](../../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1005 - Data from Local System](../../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1684.001 - Impersonation](../../../Tactics/07%20TA0005%20-%20Stealth/T1684%20-%20Social%20Engineering/T1684.001%20-%20Impersonation/README.md)
- [T1056 - Input Capture](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/README.md)
- [T1112 - Modify Registry](../../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1552 - Unsecured Credentials](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)

## Sources

- [Huntress NPPSPY 2022](https://www.huntress.com/blog/cleartext-shenanigans-gifting-user-passwords-to-adversaries-with-nppspy)
- [Polak NPPSPY 2004](https://www.blackhat.com/presentations/win-usa-04/bh-win-04-polak/bh-win-04-polak2.pdf)
