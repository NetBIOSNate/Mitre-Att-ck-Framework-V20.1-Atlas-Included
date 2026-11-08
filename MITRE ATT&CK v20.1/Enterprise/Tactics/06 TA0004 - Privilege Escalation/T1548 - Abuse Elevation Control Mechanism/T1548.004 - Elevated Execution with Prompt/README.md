# T1548.004 - Elevated Execution with Prompt

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1548 - Abuse Elevation Control Mechanism](../README.md)

Adversaries may leverage the <code>AuthorizationExecuteWithPrivileges</code> API to escalate privileges by prompting the user for credentials.(Citation: AppleDocs AuthorizationExecuteWithPrivileges) The purpose of this API is to give application developers an easy way to perform operations with root privileges, such as for application installation or updating. This API does not validate that the program requesting root privileges comes from a reputable source or has been maliciously modified. 

Although this API is deprecated, it still fully functions in the latest releases of macOS. When calling this API, the user will be prompted to enter their credentials but no checks on the origin or integrity of the program are made. The program calling the API may also load world writable files which can be modified to perform malicious behavior with elevated privileges.

Adversaries may abuse <code>AuthorizationExecuteWithPrivileges</code> to obtain root privileges in order to install malicious software on victims and install persistence mechanisms.(Citation: Death by 1000 installers; it's all broken!)(Citation: Carbon Black Shlayer Feb 2019)(Citation: OSX Coldroot RAT) This technique may be combined with [Masquerading](https://attack.mitre.org/techniques/T1036) to trick the user into granting escalated privileges to malicious code.(Citation: Death by 1000 installers; it's all broken!)(Citation: Carbon Black Shlayer Feb 2019) This technique has also been shown to work by modifying legitimate programs present on the machine that make use of this API.(Citation: Death by 1000 installers; it's all broken!)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1548/004)

**Tactics**  [Privilege Escalation](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0395 - macOS AuthorizationExecuteWithPrivileges Elevation Prompt Detection](../../../../Defenses/Detection%20Strategies/DET0395%20-%20macOS%20AuthorizationExecuteWithPrivileges%20Elevation%20Prompt%20Detection.md)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — System settings can prevent applications from running that haven't been downloaded through the Apple Store which may help mitigate some of these issues. Not allowing unsigned applications from being run may also mitigate some risk.

## Procedure examples

- [S0402 - OSX/Shlayer](../../../../Threat%20Intelligence/Software/Malware/S0402%20-%20OSX%20-%20Shlayer.md) — [OSX/Shlayer](https://attack.mitre.org/software/S0402) can escalate privileges to root by asking the user for credentials.(Citation: Carbon Black Shlayer Feb 2019) [Carbon Black Shlayer Feb 2019](https://blogs.vmware.com/security/2020/02/vmware-carbon-black-tau-threat-analysis-shlayer-macos.html)

## Sources

- [AppleDocs AuthorizationExecuteWithPrivileges](https://developer.apple.com/documentation/security/1540038-authorizationexecutewithprivileg)
- [Carbon Black Shlayer Feb 2019](https://blogs.vmware.com/security/2020/02/vmware-carbon-black-tau-threat-analysis-shlayer-macos.html)
- [Death by 1000 installers; it's all broken!](https://speakerdeck.com/patrickwardle/defcon-2017-death-by-1000-installers-its-all-broken?slide=8)
- [OSX Coldroot RAT](https://objective-see.com/blog/blog_0x2A.html)
