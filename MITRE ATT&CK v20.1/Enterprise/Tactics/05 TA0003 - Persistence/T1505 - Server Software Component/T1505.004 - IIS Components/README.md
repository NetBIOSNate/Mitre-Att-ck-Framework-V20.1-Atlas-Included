# T1505.004 - IIS Components

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1505 - Server Software Component](../README.md)

Adversaries may install malicious components that run on Internet Information Services (IIS) web servers to establish persistence. IIS provides several mechanisms to extend the functionality of the web servers. For example, Internet Server Application Programming Interface (ISAPI) extensions and filters can be installed to examine and/or modify incoming and outgoing IIS web requests. Extensions and filters are deployed as DLL files that export three functions: <code>Get{Extension/Filter}Version</code>, <code>Http{Extension/Filter}Proc</code>, and (optionally) <code>Terminate{Extension/Filter}</code>. IIS modules may also be installed to extend IIS web servers.(Citation: Microsoft ISAPI Extension Overview 2017)(Citation: Microsoft ISAPI Filter Overview 2017)(Citation: IIS Backdoor 2011)(Citation: Trustwave IIS Module 2013)

Adversaries may install malicious ISAPI extensions and filters to observe and/or modify traffic, execute commands on compromised machines, or proxy command and control traffic. ISAPI extensions and filters may have access to all IIS web requests and responses. For example, an adversary may abuse these mechanisms to modify HTTP responses in order to distribute malicious commands/content to previously comprised hosts.(Citation: Microsoft ISAPI Filter Overview 2017)(Citation: Microsoft ISAPI Extension Overview 2017)(Citation: Microsoft ISAPI Extension All Incoming 2017)(Citation: Dell TG-3390)(Citation: Trustwave IIS Module 2013)(Citation: MMPC ISAPI Filter 2012)

Adversaries may also install malicious IIS modules to observe and/or modify traffic. IIS 7.0 introduced modules that provide the same unrestricted access to HTTP requests and responses as ISAPI extensions and filters. IIS modules can be written as a DLL that exports <code>RegisterModule</code>, or as a .NET application that interfaces with ASP.NET APIs to access IIS HTTP requests.(Citation: Microsoft IIS Modules Overview 2007)(Citation: Trustwave IIS Module 2013)(Citation: ESET IIS Malware 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1505/004)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Regularly check installed IIS components to verify the integrity of the web server and identify if unexpected changes have been made.
- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Ensure IIS DLLs and binaries are signed by the correct application developers.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Restrict unallowed ISAPI extensions and filters from running by specifying a list of ISAPI extensions and filters that can run on IIS.(Citation: Microsoft ISAPICGIRestriction 2016) [Microsoft ISAPICGIRestriction 2016](https://docs.microsoft.com/en-us/iis/configuration/system.webserver/security/isapicgirestriction/)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow administrator accounts that have permissions to add IIS components to be used for day-to-day operations that may expose these permissions to potential adversaries and/or other unprivileged systems.

## Procedure examples

- [S1022 - IceApple](../../../../Threat%20Intelligence/Software/Malware/S1022%20-%20IceApple.md) — [IceApple](https://attack.mitre.org/software/S1022) is an IIS post-exploitation framework, consisting of 18 modules that provide several functionalities.(Citation: CrowdStrike IceApple May 2022) [CrowdStrike IceApple May 2022](https://www.crowdstrike.com/wp-content/uploads/2022/05/crowdstrike-iceapple-a-novel-internet-information-services-post-exploitation-framework.pdf)
- [C0022 - Operation Dream Job](../../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — During [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) targeted Windows servers running Internet Information Systems (IIS) to install C2 components.(Citation: McAfee Lazarus Jul 2020) [McAfee Lazarus Jul 2020](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/operation-north-star-a-job-offer-thats-too-good-to-be-true/?hilite=%27Operation%27%2C%27North%27%2C%27Star%27)
- [S0072 - OwaAuth](../../../../Threat%20Intelligence/Software/Malware/S0072%20-%20OwaAuth.md) — [OwaAuth](https://attack.mitre.org/software/S0072) has been loaded onto Exchange servers and disguised as an ISAPI filter (owaauth.dll). The IIS w3wp.exe process then loads the malicious DLL.(Citation: Dell TG-3390) [Dell TG-3390](https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage)
- [S0258 - RGDoor](../../../../Threat%20Intelligence/Software/Malware/S0258%20-%20RGDoor.md) — [RGDoor](https://attack.mitre.org/software/S0258) establishes persistence on webservers as an IIS module.(Citation: Unit 42 RGDoor Jan 2018)(Citation: ESET IIS Malware 2021) [Unit 42 RGDoor Jan 2018](https://researchcenter.paloaltonetworks.com/2018/01/unit42-oilrig-uses-rgdoor-iis-backdoor-targets-middle-east/) · [ESET IIS Malware 2021](https://i.blackhat.com/USA21/Wednesday-Handouts/us-21-Anatomy-Of-Native-Iis-Malware-wp.pdf)
- [C0058 - SharePoint ToolShell Exploitation](../../../../Threat%20Intelligence/Campaigns/C0058%20-%20SharePoint%20ToolShell%20Exploitation.md) — During [SharePoint ToolShell Exploitation](https://attack.mitre.org/campaigns/C0058), threat actors modified Internet Information Services (IIS) components to load suspicious .NET assemblies for persistence.(Citation: Microsoft SharePoint Exploit JUL 2025) [Microsoft SharePoint Exploit JUL 2025](https://www.microsoft.com/en-us/security/blog/2025/07/22/disrupting-active-exploitation-of-on-premises-sharepoint-vulnerabilities/#storm-2603)

## Detection strategies

- [DET0068 - Detection Strategy for T1505.004 - Malicious IIS Components](../../../../Defenses/Detection%20Strategies/DET0068%20-%20Detection%20Strategy%20for%20T1505.004%20-%20Malicious%20IIS%20Components.md)

## Sources

- [Dell TG-3390](https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage)
- [Unit 42 RGDoor Jan 2018](https://researchcenter.paloaltonetworks.com/2018/01/unit42-oilrig-uses-rgdoor-iis-backdoor-targets-middle-east/)
- [Trustwave IIS Module 2013](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/the-curious-case-of-the-malicious-iis-module/)
- [ESET IIS Malware 2021](https://i.blackhat.com/USA21/Wednesday-Handouts/us-21-Anatomy-Of-Native-Iis-Malware-wp.pdf)
- [IIS Backdoor 2011](https://web.archive.org/web/20170106175935/http:/esec-lab.sogeti.com/posts/2011/02/02/iis-backdoor.html)
- [Microsoft IIS Modules Overview 2007](https://docs.microsoft.com/en-us/iis/get-started/introduction-to-iis/iis-modules-overview)
- [Microsoft ISAPI Extension All Incoming 2017](https://docs.microsoft.com/en-us/previous-versions/iis/6.0-sdk/ms525696%28v=vs.90%29)
- [Microsoft ISAPI Extension Overview 2017](https://docs.microsoft.com/en-us/previous-versions/iis/6.0-sdk/ms525172%28v=vs.90%29)
- [Microsoft ISAPI Filter Overview 2017](https://docs.microsoft.com/en-us/previous-versions/iis/6.0-sdk/ms524610%28v=vs.90%29)
- [MMPC ISAPI Filter 2012](https://web.archive.org/web/20140804175025/http:/blogs.technet.com/b/mmpc/archive/2012/10/03/malware-signed-with-the-adobe-code-signing-certificate.aspx)
