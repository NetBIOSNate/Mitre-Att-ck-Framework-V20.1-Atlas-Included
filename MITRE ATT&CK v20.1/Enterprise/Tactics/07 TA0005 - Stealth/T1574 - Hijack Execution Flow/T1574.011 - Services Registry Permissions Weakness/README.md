# T1574.011 - Services Registry Permissions Weakness

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1574 - Hijack Execution Flow](../README.md)

Adversaries may execute their own malicious payloads by hijacking the Registry entries used by services. Flaws in the permissions for Registry keys related to services can allow adversaries to redirect the originally specified executable to one they control, launching their own code when a service starts. Windows stores local service configuration information in the Registry under <code>HKLM\SYSTEM\CurrentControlSet\Services</code>. The information stored under a service's Registry keys can be manipulated to modify a service's execution parameters through tools such as the service controller, sc.exe,  [PowerShell](https://attack.mitre.org/techniques/T1059/001), or [Reg](https://attack.mitre.org/software/S0075). Access to Registry keys is controlled through access control lists and user permissions.(Citation: Registry Key Security)(Citation: malware_hides_service)

If the permissions for users and groups are not properly set and allow access to the Registry keys for a service, adversaries may change the service's binPath/ImagePath to point to a different executable under their control. When the service starts or is restarted, the adversary-controlled program will execute, allowing the adversary to establish persistence and/or privilege escalation to the account context the service is set to execute under (local/domain account, SYSTEM, LocalService, or NetworkService).

Adversaries may also alter other Registry keys in the service’s Registry tree. For example, the <code>FailureCommand</code> key may be changed so that the service is executed in an elevated context anytime the service fails or is intentionally corrupted.(Citation: Kansa Service related collectors)(Citation: Tweet Registry Perms Weakness)

The <code>Performance</code> key contains the name of a driver service's performance DLL and the names of several exported functions in the DLL.(Citation: microsoft_services_registry_tree) If the <code>Performance</code> key is not already present and if an adversary-controlled user has the <code>Create Subkey</code> permission, adversaries may create the <code>Performance</code> key in the service’s Registry tree to point to a malicious DLL.(Citation: insecure_reg_perms)

Adversaries may also add the <code>Parameters</code> key, which can reference malicious drivers file paths. This technique has been identified to be a method of abuse by configuring DLL file paths within the <code>Parameters</code> key of a given services registry configuration. By placing and configuring the <code>Parameters</code> key to reference a malicious DLL, adversaries can ensure that their code is loaded persistently whenever the associated service or library is invoked.

For example, the registry path(Citation: MDSec) <code>HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\WinSock2\Parameters</code>(Citation: hexacorn)(Citation: gendigital) contains the <code>AutodiaDLL</code> value, which specifies the DLL to be loaded for autodial functionality. An adversary could set the <code>AutodiaDLL</code> to point to a hijacked or malicious DLL:

<code>"AutodialDLL"="c:\temp\foo.dll"</code>

This ensures persistence, as it causes the DLL (in this case, foo.dll) to be loaded each time the Winsock 2 library is invoked.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1574/011)

**Tactics**  [Execution](../../../04%20TA0002%20-%20Execution/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0427 - Detection Strategy for Hijack Execution Flow through Service Registry Premission Weakness.](../../../../Defenses/Detection%20Strategies/DET0427%20-%20Detection%20Strategy%20for%20Hijack%20Execution%20Flow%20through%20Service%20Registry%20Premission%20Weak.md)

## Mitigations

- [M1024 - Restrict Registry Permissions](../../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Ensure proper permissions are set for Registry hives to prevent users from modifying keys for system components that may lead to privilege escalation.

## Procedure examples

- [C0006 - Operation Honeybee](../../../../Threat%20Intelligence/Campaigns/C0006%20-%20Operation%20Honeybee.md) — During [Operation Honeybee](https://attack.mitre.org/campaigns/C0006), the threat actors used a batch file that modified the COMSysApp service to load a malicious ipnet.dll payload and to load a DLL into the `svchost.exe` process.(Citation: McAfee Honeybee) [McAfee Honeybee](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/)

## Sources

- [Tweet Registry Perms Weakness](https://x.com/r0wdy_/status/936365549553991680)
- [insecure_reg_perms](https://itm4n.github.io/windows-registry-rpceptmapper-eop/)
- [hexacorn](https://www.hexacorn.com/blog/2015/01/13/beyond-good-ol-run-key-part-24/)
- [Kansa Service related collectors](https://trustedsignal.blogspot.com/2014/05/kansa-service-related-collectors-and.html)
- [malware_hides_service](https://www.bleepingcomputer.com/tutorials/how-malware-hides-as-a-service/)
- [MDSec](https://www.mdsec.co.uk/2022/10/autodialdlling-your-way/)
- [Registry Key Security](https://docs.microsoft.com/en-us/windows/win32/sysinfo/registry-key-security-and-access-rights?redirectedfrom=MSDN)
- [microsoft_services_registry_tree](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/hklm-system-currentcontrolset-services-registry-tree)
- [gendigital](https://www.gendigital.com/blog/insights/research/operation-dragon-castling-apt-group-targeting-betting-companies)
