# T1547.003 - Time Providers

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may abuse time providers to execute DLLs when the system boots. The Windows Time service (W32Time) enables time synchronization across and within domains.(Citation: Microsoft W32Time Feb 2018) W32Time time providers are responsible for retrieving time stamps from hardware/network resources and outputting these values to other network clients.(Citation: Microsoft TimeProvider)

Time providers are implemented as dynamic-link libraries (DLLs) that are registered in the subkeys of `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\W32Time\TimeProviders\`.(Citation: Microsoft TimeProvider) The time provider manager, directed by the service control manager, loads and starts time providers listed and enabled under this key at system startup and/or whenever parameters are changed.(Citation: Microsoft TimeProvider)

Adversaries may abuse this architecture to establish persistence, specifically by creating a new arbitrarily named subkey  pointing to a malicious DLL in the `DllName` value. Administrator privileges are required for time provider registration, though execution will run in context of the Local Service account.(Citation: Github W32Time Oct 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/003)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Consider using Group Policy to configure and block additions/modifications to W32Time DLLs. (Citation: Microsoft W32Time May 2017) [Microsoft W32Time May 2017](https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-tools-and-settings)
- [M1024 - Restrict Registry Permissions](../../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Consider using Group Policy to configure and block modifications to W32Time parameters in the Registry. (Citation: Microsoft W32Time May 2017) [Microsoft W32Time May 2017](https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-tools-and-settings)

## Detection strategies

- [DET0122 - Detect Abuse of Windows Time Providers for Persistence](../../../../Defenses/Detection%20Strategies/DET0122%20-%20Detect%20Abuse%20of%20Windows%20Time%20Providers%20for%20Persistence.md)

## Sources

- [Github W32Time Oct 2017](https://github.com/scottlundgren/w32time)
- [Microsoft W32Time May 2017](https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-tools-and-settings)
- [Microsoft W32Time Feb 2018](https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-top)
- [Microsoft TimeProvider](https://msdn.microsoft.com/library/windows/desktop/ms725475.aspx)
- [TechNet Autoruns](https://technet.microsoft.com/en-us/sysinternals/bb963902)
