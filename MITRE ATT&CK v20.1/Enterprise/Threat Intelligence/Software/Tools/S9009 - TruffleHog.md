# S9009 - TruffleHog

[Enterprise](../../../README.md) / [Tools](README.md)

[TruffleHog](https://attack.mitre.org/software/S9009) is an open-source secrets-discovery tool that is used to search for credentials, API keys, and encryption keys across a variety of data sources and environments.(Citation: Black Hills Information Security TruffleHog January 2024)(Citation: Github TruffleSecurity Trufflehog April 2025) [TruffleHog](https://attack.mitre.org/software/S9009) has the ability to discover credentials and secrets stored in code repositories, git history, CI/CD pipelines, among other common storage locations to include filesystems and cloud storage buckets.(Citation: Black Hills Information Security TruffleHog January 2024)(Citation: Netskope Shai-Hulud November 2025)(Citation: Github TruffleSecurity Trufflehog April 2025) [TruffleHog](https://attack.mitre.org/software/S9009) was first released by its author in 2016.(Citation: Github TruffleSecurity Trufflehog April 2025)

[MITRE ATT&CK record](https://attack.mitre.org/software/S9009)

**Platforms**  [IaaS](../../../Platforms/IaaS.md), [Linux](../../../Platforms/Linux.md), [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1078.004 - Cloud Accounts](../../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.004%20-%20Cloud%20Accounts/README.md)
- [T1059.009 - Cloud API](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.009%20-%20Cloud%20API/README.md)
- [T1580 - Cloud Infrastructure Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1580%20-%20Cloud%20Infrastructure%20Discovery/README.md)
- [T1552.005 - Cloud Instance Metadata API](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.005%20-%20Cloud%20Instance%20Metadata%20API/README.md)
- [T1555.006 - Cloud Secrets Management Stores](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.006%20-%20Cloud%20Secrets%20Management%20Stores/README.md)
- [T1526 - Cloud Service Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1526%20-%20Cloud%20Service%20Discovery/README.md)
- [T1619 - Cloud Storage Object Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1619%20-%20Cloud%20Storage%20Object%20Discovery/README.md)
- [T1213.003 - Code Repositories](../../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.003%20-%20Code%20Repositories/README.md)
- [T1213.001 - Confluence](../../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.001%20-%20Confluence/README.md)
- [T1552.001 - Credentials In Files](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1530 - Data from Cloud Storage](../../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1005 - Data from Local System](../../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1213.005 - Messaging Applications](../../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.005%20-%20Messaging%20Applications/README.md)
- [T1213.002 - Sharepoint](../../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.002%20-%20Sharepoint/README.md)
- [T1528 - Steal Application Access Token](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1528%20-%20Steal%20Application%20Access%20Token/README.md)

## Sources

- [Black Hills Information Security TruffleHog January 2024](https://www.blackhillsinfosec.com/rooting-for-secrets-with-trufflehog/)
- [Netskope Shai-Hulud November 2025](https://www.netskope.com/blog/shai-hulud-2-0-aggressive-automated-one-of-fastest-spreading-npm-supply-chain-attacks-ever-observed)
- [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)
