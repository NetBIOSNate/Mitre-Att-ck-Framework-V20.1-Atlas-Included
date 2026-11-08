# S0683 - Peirates

[Enterprise](../../../README.md) / [Tools](README.md)

[Peirates](https://attack.mitre.org/software/S0683) is a post-exploitation Kubernetes exploitation framework with a focus on gathering service account tokens for lateral movement and privilege escalation. The tool is written in GoLang and publicly available on GitHub.(Citation: Peirates GitHub)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0683)

**Platforms**  [Containers](../../../Platforms/Containers.md)

## Techniques used

- [T1550.001 - Application Access Token](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.001%20-%20Application%20Access%20Token/README.md)
- [T1078.004 - Cloud Accounts](../../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.004%20-%20Cloud%20Accounts/README.md)
- [T1552.005 - Cloud Instance Metadata API](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.005%20-%20Cloud%20Instance%20Metadata%20API/README.md)
- [T1619 - Cloud Storage Object Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1619%20-%20Cloud%20Storage%20Object%20Discovery/README.md)
- [T1609 - Container Administration Command](../../../Tactics/04%20TA0002%20-%20Execution/T1609%20-%20Container%20Administration%20Command/README.md)
- [T1613 - Container and Resource Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1613%20-%20Container%20and%20Resource%20Discovery/README.md)
- [T1552.007 - Container API](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.007%20-%20Container%20API/README.md)
- [T1530 - Data from Cloud Storage](../../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1610 - Deploy Container](../../../Tactics/04%20TA0002%20-%20Execution/T1610%20-%20Deploy%20Container/README.md)
- [T1611 - Escape to Host](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1611%20-%20Escape%20to%20Host/README.md)
- [T1046 - Network Service Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1528 - Steal Application Access Token](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1528%20-%20Steal%20Application%20Access%20Token/README.md)

## Used by

- [G0139 - TeamTNT](../../Groups/G0139%20-%20TeamTNT.md)

## Sources

- [Peirates GitHub](https://github.com/inguardians/peirates)
