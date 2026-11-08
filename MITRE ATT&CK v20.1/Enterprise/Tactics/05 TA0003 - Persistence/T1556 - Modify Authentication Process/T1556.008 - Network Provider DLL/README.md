# T1556.008 - Network Provider DLL

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1556 - Modify Authentication Process](../README.md)

Adversaries may register malicious network provider dynamic link libraries (DLLs) to capture cleartext user credentials during the authentication process. Network provider DLLs allow Windows to interface with specific network protocols and can also support add-on credential management functions.(Citation: Network Provider API) During the logon process, Winlogon (the interactive logon module) sends credentials to the local `mpnotify.exe` process via RPC. The `mpnotify.exe` process then shares the credentials in cleartext with registered credential managers when notifying that a logon event is happening.(Citation: NPPSPY - Huntress)(Citation: NPPSPY Video)(Citation: NPLogonNotify) 

Adversaries can configure a malicious network provider DLL to receive credentials from `mpnotify.exe`.(Citation: NPPSPY) Once installed as a credential manager (via the Registry), a malicious DLL can receive and save credentials each time a user logs onto a Windows workstation or domain via the `NPLogonNotify()` function.(Citation: NPLogonNotify)

Adversaries may target planting malicious network provider DLLs on systems known to have increased logon activity and/or administrator logon activity, such as servers and domain controllers.(Citation: NPPSPY - Huntress)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1556/008)

**Tactics**  [Persistence](../../README.md), [Defense Impairment](../../../08%20TA0112%20-%20Defense%20Impairment/README.md), [Credential Access](../../../09%20TA0006%20-%20Credential%20Access/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Periodically review for new and unknown network provider DLLs within the Registry (`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\<NetworkProviderName>\NetworkProvider\ProviderPath`). Ensure only valid network provider DLLs are registered. The name of these can be found in the Registry key at `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\NetworkProvider\Order`, and have corresponding service subkey pointing to a DLL at `HKEY_LOCAL_MACHINE\SYSTEM\CurrentC ontrolSet\Services\<NetworkProviderName>\NetworkProvider`.
- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Starting in Windows 11 22H2, the `EnableMPRNotifications` policy can be disabled through Group Policy or through a configuration service provider to prevent Winlogon from sending credentials to network providers.(Citation: EnableMPRNotifications) [EnableMPRNotifications](https://learn.microsoft.com/en-us/windows/client-management/mdm/policy-csp-windowslogon)
- [M1024 - Restrict Registry Permissions](../../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Restrict Registry permissions to disallow the modification of sensitive Registry keys such as `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\NetworkProvider\Order`.

## Detection strategies

- [DET0580 - Detect Network Provider DLL Registration and Credential Capture](../../../../Defenses/Detection%20Strategies/DET0580%20-%20Detect%20Network%20Provider%20DLL%20Registration%20and%20Credential%20Capture.md)

## Sources

- [NPPSPY - Huntress](https://www.huntress.com/blog/cleartext-shenanigans-gifting-user-passwords-to-adversaries-with-nppspy)
- [NPPSPY Video](https://www.youtube.com/watch?v=ggY3srD9dYs)
- [NPPSPY](https://github.com/gtworek/PSBits/tree/master/PasswordStealing/NPPSpy)
- [Network Provider API](https://learn.microsoft.com/en-us/windows/win32/secauthn/network-provider-api)
- [NPLogonNotify](https://learn.microsoft.com/en-us/windows/win32/api/npapi/nf-npapi-nplogonnotify)
