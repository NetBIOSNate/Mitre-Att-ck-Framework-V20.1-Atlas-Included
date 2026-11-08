# G1056 - TeamPCP

[Enterprise](../../README.md) / [Groups](README.md)

[TeamPCP](https://attack.mitre.org/groups/G1056) is a financially-motivated, cloud-native threat group that has been active since at least September 2025. Initially focused on ransomware and cryptocurrency theft, [TeamPCP](https://attack.mitre.org/groups/G1056) shifted in early 2026 to systematic, worm-driven credential theft and software supply chain attacks targeting Continuous Integration and Continuous Delivery (CI/CD) workflows. [TeamPCP](https://attack.mitre.org/groups/G1056) has monetized access through extortion and through partnerships with ransomware actors including Vect and CipherForce.(Citation: Wiz TeamPCP Profile MAY 2026)(Citation: Wiz Trivy Compromise MAR 2026)(Citation: Aqua Security Trivy Compromise MAR 2026)(Citation: Aqua Security Blog Trivy Compromise APR 2026)(Citation: Palo Alto TeamPCP MAR 2026)(Citation: Trend Micro TeamPCP MAY 2026)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1056)

## Aliases

- PCPCat
- ShellForce
- DeadCatx3
- SHADOW-WATER-058
- UNC6780

## Techniques used

- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1583 - Acquire Infrastructure](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/README.md)
- [T1550.001 - Application Access Token](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.001%20-%20Application%20Access%20Token/README.md)
- [T1078.004 - Cloud Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.004%20-%20Cloud%20Accounts/README.md)
- [T1555.006 - Cloud Secrets Management Stores](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.006%20-%20Cloud%20Secrets%20Management%20Stores/README.md)
- [T1553.002 - Code Signing](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.002%20-%20Code%20Signing/README.md)
- [T1195.001 - Compromise Software Dependencies and Development Tools](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.001%20-%20Compromise%20Software%20Dependencies%20and%20Development%20Tools/README.md)
- [T1059.013 - Container CLI/API](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.013%20-%20Container%20CLI%20-%20API/README.md)
- [T1485 - Data Destruction](../../Tactics/15%20TA0040%20-%20Impact/T1485%20-%20Data%20Destruction/README.md)
- [T1486 - Data Encrypted for Impact](../../Tactics/15%20TA0040%20-%20Impact/T1486%20-%20Data%20Encrypted%20for%20Impact/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1610 - Deploy Container](../../Tactics/04%20TA0002%20-%20Execution/T1610%20-%20Deploy%20Container/README.md)
- [T1583.001 - Domains](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.001%20-%20Domains/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1657 - Financial Theft](../../Tactics/15%20TA0040%20-%20Impact/T1657%20-%20Financial%20Theft/README.md)
- [T1564.001 - Hidden Files and Directories](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.001%20-%20Hidden%20Files%20and%20Directories/README.md)
- [T1176.002 - IDE Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.002%20-%20IDE%20Extensions/README.md)
- [T1684.001 - Impersonation](../../Tactics/07%20TA0005%20-%20Stealth/T1684%20-%20Social%20Engineering/T1684.001%20-%20Impersonation/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1546.016 - Installer Packages](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.016%20-%20Installer%20Packages/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1587.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.001%20-%20Malware/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1677 - Poisoned Pipeline Execution](../../Tactics/04%20TA0002%20-%20Execution/T1677%20-%20Poisoned%20Pipeline%20Execution/README.md)
- [T1552.004 - Private Keys](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.004%20-%20Private%20Keys/README.md)
- [T1059.006 - Python](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1547.001 - Registry Run Keys / Startup Folder](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.001%20-%20Registry%20Run%20Keys%20-%20Startup%20Folder/README.md)
- [T1583.004 - Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.004%20-%20Server/README.md)
- [T1585.001 - Social Media Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/T1585.001%20-%20Social%20Media%20Accounts/README.md)
- [T1528 - Steal Application Access Token](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1528%20-%20Steal%20Application%20Access%20Token/README.md)
- [T1027.003 - Steganography](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.003%20-%20Steganography/README.md)
- [T1543.002 - Systemd Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.002%20-%20Systemd%20Service/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1608.001 - Upload Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1608%20-%20Stage%20Capabilities/T1608.001%20-%20Upload%20Malware/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1583.006 - Web Services](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.006%20-%20Web%20Services/README.md)
- [T1683.001 - Written Content](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1683%20-%20Generate%20Content/T1683.001%20-%20Written%20Content/README.md)

## Software used

- [S9042 - CanisterWorm](../Software/Malware/S9042%20-%20CanisterWorm.md)
- [S9043 - Mini Shai-Hulud](../Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md)
- [S9041 - TeamPCP Cloud Stealer](../Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md)

## Sources

- [Aqua Security Trivy Compromise MAR 2026](https://github.com/aquasecurity/trivy/security/advisories/GHSA-69fq-xp46-6x23)
- [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know)
- [Google AI Threat Tracker MAY 2026](https://cloud.google.com/blog/topics/threat-intelligence/ai-vulnerability-exploitation-initial-access)
- [Wiz Trivy Compromise MAR 2026](https://www.wiz.io/blog/trivy-compromised-teampcp-supply-chain-attack)
- [Trend Micro TeamPCP MAY 2026](https://www.trendmicro.com/en_us/research/26/e/analyzing-teampcp-supply-chain-attacks.html)
- [Palo Alto TeamPCP MAR 2026](https://unit42.paloaltonetworks.com/teampcp-supply-chain-attacks/)
- [Wiz TeamPCP Profile MAY 2026](https://threats.wiz.io/all-actors/teampcp)
