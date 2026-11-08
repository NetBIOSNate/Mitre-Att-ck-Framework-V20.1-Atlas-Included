# T1048 - Exfiltration Over Alternative Protocol

[Enterprise](../../../README.md) / [Exfiltration](../README.md)

Adversaries may steal data by exfiltrating it over a different protocol than that of the existing command and control channel. The data may also be sent to an alternate network location from the main command and control server.  

Alternate protocols include FTP, SMTP, HTTP/S, DNS, SMB, or any other network protocol not being used as the main command and control channel. Adversaries may also opt to encrypt and/or obfuscate these alternate channels. 

[Exfiltration Over Alternative Protocol](https://attack.mitre.org/techniques/T1048) can be done using various common operating system utilities such as [Net](https://attack.mitre.org/software/S0039)/SMB or FTP.(Citation: Palo Alto OilRig Oct 2016) On macOS and Linux <code>curl</code> may be used to invoke protocols such as HTTP/S or FTP/S to exfiltrate data from a system.(Citation: 20 macOS Common Tools and Techniques)

Many IaaS and SaaS platforms (such as Microsoft Exchange, Microsoft SharePoint, GitHub, and AWS S3) support the direct download of files, emails, source code, and other sensitive information via the web console or [Cloud API](https://attack.mitre.org/techniques/T1059/009).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1048)

**Tactics**  [Exfiltration](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [IaaS](../../../Platforms/IaaS.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1048.002 - Exfiltration Over Asymmetric Encrypted Non-C2 Protocol](T1048.002%20-%20Exfiltration%20Over%20Asymmetric%20Encrypted%20Non-C2%20Protocol/README.md)
- [T1048.001 - Exfiltration Over Symmetric Encrypted Non-C2 Protocol](T1048.001%20-%20Exfiltration%20Over%20Symmetric%20Encrypted%20Non-C2%20Protocol/README.md)
- [T1048.003 - Exfiltration Over Unencrypted Non-C2 Protocol](T1048.003%20-%20Exfiltration%20Over%20Unencrypted%20Non-C2%20Protocol/README.md)

## Detection strategies

- [DET0131 - Behavioral Detection Strategy for Exfiltration Over Alternative Protocol](../../../Defenses/Detection%20Strategies/DET0131%20-%20Behavioral%20Detection%20Strategy%20for%20Exfiltration%20Over%20Alternative%20Protocol.md)

## Procedure examples

- [S0677 - AADInternals](../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can directly download cloud user data such as OneDrive files.(Citation: AADInternals Documentation) [AADInternals Documentation](https://o365blog.com/aadinternals)
- [S0482 - Bundlore](../../../Threat%20Intelligence/Software/Malware/S0482%20-%20Bundlore.md) — [Bundlore](https://attack.mitre.org/software/S0482) uses the <code>curl -s -L -o</code> command to exfiltrate archived data to a URL.(Citation: 20 macOS Common Tools and Techniques) [20 macOS Common Tools and Techniques](https://labs.sentinelone.com/20-common-tools-techniques-used-by-macos-threat-actors-malware/)
- [S0631 - Chaes](../../../Threat%20Intelligence/Software/Malware/S0631%20-%20Chaes.md) — [Chaes](https://attack.mitre.org/software/S0631) has exfiltrated its collected data from the infected machine to the C2, sometimes using the MIME protocol.(Citation: Cybereason Chaes Nov 2020) [Cybereason Chaes Nov 2020](https://www.cybereason.com/hubfs/dam/collateral/reports/11-2020-Chaes-e-commerce-malware-research.pdf)
- [S0503 - FrameworkPOS](../../../Threat%20Intelligence/Software/Malware/S0503%20-%20FrameworkPOS.md) — [FrameworkPOS](https://attack.mitre.org/software/S0503) can use DNS tunneling for exfiltration of credit card data.(Citation: SentinelOne FrameworkPOS September 2019) [SentinelOne FrameworkPOS September 2019](https://labs.sentinelone.com/fin6-frameworkpos-point-of-sale-malware-analysis-internals-2/)
- [S0203 - Hydraq](../../../Threat%20Intelligence/Software/Malware/S0203%20-%20Hydraq.md) — [Hydraq](https://attack.mitre.org/software/S0203) connects to a predefined domain on port 443 to exfil gathered information.(Citation: Symantec Hydraq Jan 2010) [Symantec Hydraq Jan 2010](https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99)
- [S0641 - Kobalos](../../../Threat%20Intelligence/Software/Malware/S0641%20-%20Kobalos.md) — [Kobalos](https://attack.mitre.org/software/S0641) can exfiltrate credentials over the network via UDP.(Citation: ESET Kobalos Jan 2021) [ESET Kobalos Jan 2021](https://www.welivesecurity.com/wp-content/uploads/2021/01/ESET_Kobalos.pdf)
- [G1040 - Play](../../../Threat%20Intelligence/Groups/G1040%20-%20Play.md) — [Play](https://attack.mitre.org/groups/G1040) has used WinSCP to exfiltrate data to actor-controlled accounts.(Citation: CISA Play Ransomware Advisory December 2023)(Citation: Trend Micro Ransomware Spotlight Play July 2023) [CISA Play Ransomware Advisory December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-352a) · [Trend Micro Ransomware Spotlight Play July 2023](https://www.trendmicro.com/vinfo/us/security/news/ransomware-spotlight/ransomware-spotlight-play)
- [S0428 - PoetRAT](../../../Threat%20Intelligence/Software/Malware/S0428%20-%20PoetRAT.md) — [PoetRAT](https://attack.mitre.org/software/S0428) has used a .NET tool named dog.exe to exiltrate information over an e-mail account.(Citation: Talos PoetRAT April 2020) [Talos PoetRAT April 2020](https://blog.talosintelligence.com/2020/04/poetrat-covid-19-lures.html)
- [G0139 - TeamTNT](../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has sent locally staged files with collected credentials to C2 servers using cURL.(Citation: Cisco Talos Intelligence Group) [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/)

## Mitigations

- [M1057 - Data Loss Prevention](../../../Defenses/Mitigations/M1057%20-%20Data%20Loss%20Prevention.md) — Data loss prevention can detect and block sensitive data being uploaded via web browsers.
- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Enforce proxies and use dedicated servers for services such as DNS and only allow those systems to communicate over respective ports/protocols, instead of all systems within a network. Cloud service providers support IP-based restrictions when accessing cloud resources. Consider using IP allowlisting along with user account management to ensure that data access is restricted not only to valid users but only from expected IP ranges to mitigate the use of stolen credentials to access data.
- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary command and control infrastructure and malware can be used to mitigate activity at the network level.
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Follow best practices for network firewall configurations to allow only necessary ports and traffic to enter and exit the network.(Citation: TechNet Firewall Design) [TechNet Firewall Design](https://technet.microsoft.com/en-us/library/cc700828.aspx)
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Use access control lists on cloud storage systems and objects.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Configure user permissions groups and roles for access to cloud storage.(Citation: Microsoft Azure Storage Security, 2019) Implement strict Identity and Access Management (IAM) controls to prevent access to storage solutions except for the applications, users, and services that require access.(Citation: Amazon S3 Security, 2019) Ensure that temporary access tokens are issued rather than permanent credentials, especially when access is being granted to entities outside of the internal security boundary.(Citation: Amazon AWS Temporary Security Credentials) [Amazon S3 Security, 2019](https://aws.amazon.com/premiumsupport/knowledge-center/secure-s3-resources/) · [Amazon  AWS Temporary Security Credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html) · [Microsoft Azure Storage Security, 2019](https://docs.microsoft.com/en-us/azure/storage/common/storage-security-guide)

## Sources

- [University of Birmingham C2](https://arxiv.org/pdf/1408.1136)
- [Palo Alto OilRig Oct 2016](http://researchcenter.paloaltonetworks.com/2016/10/unit42-oilrig-malware-campaign-updates-toolset-and-expands-targets/)
- [20 macOS Common Tools and Techniques](https://labs.sentinelone.com/20-common-tools-techniques-used-by-macos-threat-actors-malware/)
