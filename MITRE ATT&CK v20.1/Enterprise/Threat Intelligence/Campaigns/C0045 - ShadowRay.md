# C0045 - ShadowRay

[Enterprise](../../README.md) / [Campaigns](README.md)

[ShadowRay](https://attack.mitre.org/campaigns/C0045) was a campaign that began in late 2023 targeting the education, cryptocurrency, biopharma, and other sectors through a vulnerability (CVE-2023-48022) in the Ray AI framework named ShadowRay. According to security researchers [ShadowRay](https://attack.mitre.org/campaigns/C0045) was the first known instance of AI workloads being activley exploited in the wild through vulnerabilities in AI infrastructure. CVE-2023-48022, which allows access to compute resources and sensitive data for exposed instances, remains unpatched and has been disputed by the vendor as they maintain that Ray is not intended for use outside of a strictly controlled network environment.(Citation: Oligo ShadowRay Campaign MAR 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0045)

## Techniques used

- [T1003.008 - /etc/passwd and /etc/shadow](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.008%20-%20etc%20-%20passwd%20and%20-%20etc%20-%20shadow/README.md)
- [T1496.001 - Compute Hijacking](../../Tactics/15%20TA0040%20-%20Impact/T1496%20-%20Resource%20Hijacking/T1496.001%20-%20Compute%20Hijacking/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1068 - Exploitation for Privilege Escalation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1068%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1059.006 - Python](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1546.004 - Unix Shell Configuration Modification](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.004%20-%20Unix%20Shell%20Configuration%20Modification/README.md)

## Sources

- [Oligo ShadowRay Campaign MAR 2024](https://www.oligo.security/blog/shadowray-attack-ai-workloads-actively-exploited-in-the-wild)
