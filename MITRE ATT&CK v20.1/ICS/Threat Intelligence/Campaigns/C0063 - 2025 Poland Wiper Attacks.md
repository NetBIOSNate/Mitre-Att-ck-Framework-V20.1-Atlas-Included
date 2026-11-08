# C0063 - 2025 Poland Wiper Attacks

[ICS](../../README.md) / [Campaigns](README.md)

[2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063) is a Russian state-sponsored campaign that conducted destructive cyberattacks against Polish energy infrastructure in December 2025. Targets included more than 30 wind and photovoltaic farms, a combined heat and power (CHP) plant, and a manufacturing sector company. The attacks on the distributed energy resources (DER) disrupted communications between affected facilities and the distribution system operator, but did not impact electricity generation or heat supply. Across the campaign, threat actors deployed two previously undocumented wiper tools, [DynoWiper](https://attack.mitre.org/software/S9038), a Windows-based wiper and [LazyWiper](https://attack.mitre.org/software/S9039), a PowerShell wiper, distributed via malicious Group Policy Objects. At the CHP plant, threat actors had maintained access since at least March 2025, using that foothold to obtain credentials and move laterally before attempting wiper deployment. Some reporting has assessed the activity to be consistent with Russian Federal Security Service (FSB) threat activity group [Dragonfly](https://attack.mitre.org/groups/G0035), also tracked as STATIC TUNDRA, while other reporting attributes the destructive wiper activities to the Russian General Staff Main Intelligence Directorate (GRU) threat activity group ELECTRUM, also tracked as [Sandworm Team](https://attack.mitre.org/groups/G0034).(Citation: CERT Polska)(Citation: Dragos ELECTRUM JAN 2026)(Citation: ESET DynoWiper JAN 2026)(Citation: ESET DynoWiper Update JAN 2026)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0063)

## Aliases

- 2025 Poland Wiper Campaign

## Techniques used

- [T0846.002 - Broadcast Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.002%20-%20Broadcast%20Discovery/README.md)
- [T0892 - Change Credential](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0892%20-%20Change%20Credential/README.md)
- [T0885 - Commonly Used Port](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0885%20-%20Commonly%20Used%20Port/README.md)
- [T0809 - Data Destruction](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0809%20-%20Data%20Destruction/README.md)
- [T1694.001 - Default Credentials](../../Tactics/03%20TA0110%20-%20Persistence/T1694%20-%20Insecure%20Credentials/T1694.001%20-%20Default%20Credentials/README.md)
- [T0816 - Device Restart/Shutdown](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T0822 - External Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0822%20-%20External%20Remote%20Services/README.md)
- [T0823 - Graphical User Interface](../../Tactics/02%20TA0104%20-%20Execution/T0823%20-%20Graphical%20User%20Interface/README.md)
- [T0827 - Loss of Control](../../Tactics/12%20TA0105%20-%20Impact/T0827%20-%20Loss%20of%20Control/README.md)
- [T0829 - Loss of View](../../Tactics/12%20TA0105%20-%20Impact/T0829%20-%20Loss%20of%20View/README.md)
- [T0840 - Network Connection Enumeration](../../Tactics/06%20TA0102%20-%20Discovery/T0840%20-%20Network%20Connection%20Enumeration/README.md)
- [T0846.001 - Port Scan](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.001%20-%20Port%20Scan/README.md)
- [T1701.001 - PowerShell](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.001%20-%20PowerShell/README.md)
- [T0886 - Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0886%20-%20Remote%20Services/README.md)
- [T0846 - Remote System Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/README.md)
- [T0888 - Remote System Information Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0888%20-%20Remote%20System%20Information%20Discovery/README.md)
- [T0852 - Screen Capture](../../Tactics/08%20TA0100%20-%20Collection/T0852%20-%20Screen%20Capture/README.md)
- [T1693.001 - System Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.001%20-%20System%20Firmware/README.md)
- [T0882 - Theft of Operational Information](../../Tactics/12%20TA0105%20-%20Impact/T0882%20-%20Theft%20of%20Operational%20Information/README.md)
- [T1701.003 - Unix Shell](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.003%20-%20Unix%20Shell/README.md)
- [T0859 - Valid Accounts](../../Tactics/03%20TA0110%20-%20Persistence/T0859%20-%20Valid%20Accounts/README.md)

## Sources

- [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [ESET DynoWiper Update JAN 2026](https://www.welivesecurity.com/en/eset-research/dynowiper-update-technical-analysis-attribution/)
- [ESET DynoWiper JAN 2026](https://www.eset.com/us/about/newsroom/research/eset-research-russian-sandwormapt-attacks-energy-company-poland-with-dynowiper/)
- [Dragos ELECTRUM JAN 2026](https://5943619.hs-sites.com/hubfs/Reports/dragos-2025-poland-attack-report.pdf)
