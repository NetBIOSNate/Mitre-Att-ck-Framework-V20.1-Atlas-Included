# T1505.001 - SQL Stored Procedures

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1505 - Server Software Component](../README.md)

Adversaries may abuse SQL stored procedures to establish persistent access to systems. SQL Stored Procedures are code that can be saved and reused so that database users do not waste time rewriting frequently used SQL queries. Stored procedures can be invoked via SQL statements to the database using the procedure name or via defined events (e.g. when a SQL server application is started/restarted).

Adversaries may craft malicious stored procedures that can provide a persistence mechanism in SQL database servers.(Citation: NetSPI Startup Stored Procedures)(Citation: Kaspersky MSSQL Aug 2019) To execute operating system commands through SQL syntax the adversary may have to enable additional functionality, such as xp_cmdshell for MSSQL Server.(Citation: NetSPI Startup Stored Procedures)(Citation: Kaspersky MSSQL Aug 2019)(Citation: Microsoft xp_cmdshell 2017) 

Microsoft SQL Server can enable common language runtime (CLR) integration. With CLR integration enabled, application developers can write stored procedures using any .NET framework language (e.g. VB .NET, C#, etc.).(Citation: Microsoft CLR Integration 2017) Adversaries may craft or modify CLR assemblies that are linked to stored procedures since these CLR assemblies can be made to execute arbitrary commands.(Citation: NetSPI SQL Server CLR)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1505/001)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Regularly check component software on critical services that adversaries may target for persistence to verify the integrity of the systems and identify if unexpected changes have been made.
- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Ensure all application component binaries are signed by the correct application developers.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow administrator accounts that have permissions to add component software on these services to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) used various MS-SQL stored procedures.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [S0603 - Stuxnet](../../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) used xp_cmdshell to store and execute SQL code.(Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Detection strategies

- [DET0181 - Detection Strategy for SQL Stored Procedures Abuse via T1505.001](../../../../Defenses/Detection%20Strategies/DET0181%20-%20Detection%20Strategy%20for%20SQL%20Stored%20Procedures%20Abuse%20via%20T1505.001.md)

## Sources

- [Microsoft CLR Integration 2017](https://docs.microsoft.com/en-us/sql/relational-databases/clr-integration/common-language-runtime-integration-overview?view=sql-server-2017)
- [Microsoft xp_cmdshell 2017](https://docs.microsoft.com/en-us/sql/relational-databases/system-stored-procedures/xp-cmdshell-transact-sql?view=sql-server-2017)
- [Kaspersky MSSQL Aug 2019](https://securelist.com/malicious-tasks-in-ms-sql-server/92167/)
- [NetSPI Startup Stored Procedures](https://www.netspi.com/blog/technical-blog/network-penetration-testing/sql-server-persistence-part-1-startup-stored-procedures/)
- [NetSPI SQL Server CLR](https://www.netspi.com/blog/technical-blog/adversary-simulation/attacking-sql-server-clr-assemblies/)
