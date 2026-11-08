# C0062 - Anthropic AI-orchestrated Campaign

[Enterprise](../../README.md) / [Campaigns](README.md)

The [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062) was conducted in September 2025 by a likely China nexus espionage actor identified as GTG-1002. The [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062) was a highly coordinated operation that manipulated Claude Code to perform reconnaissance, vulnerability discovery, exploitation, lateral movement, credential harvesting, data analysis, and exfiltration operations at approximately 30 entities in the technology, financial, chemical, and government sectors. During the [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062), human operators used Claude Code agents and Model Context Protocol (MCP) tools to automate cyber operations. Operators broke attacks into discrete tasks, used crafted prompts,  and established personas to bypass AI guardrails, enabling the agents to execute the operations with minimal human involvement.(Citation: Anthropic AI Orchestrated Campaign NOV 2025)(Citation: Anthropic Disrupting AI Espionage NOV 2025)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0062)

## Techniques used

- [T1087 - Account Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/README.md)
- [T1588.007 - Artificial Intelligence](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.007%20-%20Artificial%20Intelligence/README.md)
- [T1119 - Automated Collection](../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1592.004 - Client Configurations](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1592%20-%20Gather%20Victim%20Host%20Information/T1592.004%20-%20Client%20Configurations/README.md)
- [T1552.001 - Credentials In Files](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1213.006 - Databases](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.006%20-%20Databases/README.md)
- [T1699 - Direct Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1699%20-%20Direct%20Prompt%20Injection/README.md)
- [T1567 - Exfiltration Over Web Service](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1587.004 - Exploits](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.004%20-%20Exploits/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1683 - Generate Content](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1683%20-%20Generate%20Content/README.md)
- [T1136.001 - Local Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.001%20-%20Local%20Account/README.md)
- [T1078.003 - Local Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.003%20-%20Local%20Accounts/README.md)
- [T1074.001 - Local Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.001%20-%20Local%20Data%20Staging/README.md)
- [T1046 - Network Service Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1590.004 - Network Topology](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1590%20-%20Gather%20Victim%20Network%20Information/T1590.004%20-%20Network%20Topology/README.md)
- [T1595.001 - Scanning IP Blocks](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/T1595.001%20-%20Scanning%20IP%20Blocks/README.md)
- [T1584.004 - Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.004%20-%20Server/README.md)
- [T1592.002 - Software](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1592%20-%20Gather%20Victim%20Host%20Information/T1592.002%20-%20Software/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1595.002 - Vulnerability Scanning](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/T1595.002%20-%20Vulnerability%20Scanning/README.md)

## Sources

- [Anthropic Disrupting AI Espionage NOV 2025](https://www.anthropic.com/news/disrupting-AI-espionage)
- [Anthropic AI Orchestrated Campaign NOV 2025](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf)
