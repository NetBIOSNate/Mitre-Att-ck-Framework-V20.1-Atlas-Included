# T1651 - Cloud Administration Command

[Enterprise](../../../README.md) / [Execution](../README.md)

Adversaries may abuse cloud management services to execute commands within virtual machines. Resources such as AWS Systems Manager, Azure RunCommand, and Runbooks allow users to remotely run scripts in virtual machines by leveraging installed virtual machine agents.(Citation: AWS Systems Manager Run Command)(Citation: Microsoft Run Command)

If an adversary gains administrative access to a cloud environment, they may be able to abuse cloud management services to execute commands in the environment’s virtual machines. Additionally, an adversary that compromises a service provider or delegated administrator account may similarly be able to leverage a [Trusted Relationship](https://attack.mitre.org/techniques/T1199) to execute commands in connected virtual machines.(Citation: MSTIC Nobelium Oct 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1651)

**Tactics**  [Execution](../README.md)

**Platforms**  [IaaS](../../../Platforms/IaaS.md)

## Procedure examples

- [S0677 - AADInternals](../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can execute commands on Azure virtual machines using the VM agent.(Citation: AADInternals Root Access to Azure VMs) [AADInternals Root Access to Azure VMs](https://aadinternals.com/post/azurevms/)
- [G0016 - APT29](../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has used Azure Run Command and Azure Admin-on-Behalf-of (AOBO) to execute code on virtual machines.(Citation: MSTIC Nobelium Oct 2021) [MSTIC Nobelium Oct 2021](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/)
- [S1091 - Pacu](../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can run commands on EC2 instances using AWS Systems Manager Run Command.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [G1055 - VOID MANTICORE](../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has abused built-in remote wipe or factory reset commands to wipe devices managed within an organization’s Cloud management solution impacting laptops, servers, and mobile devices.(Citation: Palo Alto VOID MANTICORE Iran Cyber Threats March 2026) [Palo Alto VOID MANTICORE Iran Cyber Threats March 2026](https://unit42.paloaltonetworks.com/evolution-of-iran-cyber-threats/)

## Mitigations

- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit the number of cloud accounts with permissions to remotely execute commands on virtual machines, and ensure that these are not used for day-to-day operations. In Azure, limit the number of accounts with the roles Azure Virtual Machine Contributer and above, and consider using temporary Just-in-Time (JIT) roles to avoid permanently assigning privileged access to virtual machines.(Citation: Mandiant Azure Run Command 2021) [Mandiant Azure Run Command 2021](https://www.mandiant.com/resources/blog/azure-run-command-dummies)

## Detection strategies

- [DET0545 - Detection Strategy for Cloud Administration Command](../../../Defenses/Detection%20Strategies/DET0545%20-%20Detection%20Strategy%20for%20Cloud%20Administration%20Command.md)

## Sources

- [AWS Systems Manager Run Command](https://docs.aws.amazon.com/systems-manager/latest/userguide/run-command.html)
- [MSTIC Nobelium Oct 2021](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/)
- [Microsoft Run Command](https://learn.microsoft.com/en-us/azure/virtual-machines/run-command-overview)
