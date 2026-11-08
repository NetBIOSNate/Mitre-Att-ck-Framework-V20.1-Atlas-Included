# T1187 - Forced Authentication

[Enterprise](../../../README.md) / [Credential Access](../README.md)

Adversaries may gather credential material by invoking or forcing a user to automatically provide authentication information through a mechanism in which they can intercept that information.

The Server Message Block (SMB) protocol is commonly used in Windows networks for authentication and communication between systems for access to resources and file sharing. When a Windows system attempts to connect to an SMB resource it will automatically attempt to authenticate and send credential information for the current user to the remote system.(Citation: Wikipedia Server Message Block) This behavior is typical in enterprise environments so that users do not need to enter credentials to access network resources.

Web Distributed Authoring and Versioning (WebDAV) is also typically used by Windows systems as a backup protocol when SMB is blocked or fails. WebDAV is an extension of HTTP and will typically operate over TCP ports 80 and 443.(Citation: Didier Stevens WebDAV Traffic)(Citation: Microsoft Managing WebDAV Security)

Adversaries may take advantage of this behavior to gain access to user account hashes through forced SMB/WebDAV authentication. An adversary can send an attachment to a user through spearphishing that contains a resource link to an external server controlled by the adversary  (i.e. [Template Injection](https://attack.mitre.org/techniques/T1221)), or place a specially crafted file on navigation path for privileged accounts (e.g. .SCF file placed on desktop) or on a publicly accessible share to be accessed by victim(s). When the user's system accesses the untrusted resource, it will attempt authentication and send information, including the user's hashed credentials, over SMB to the adversary-controlled server.(Citation: GitHub Hashjacking) With access to the credential hash, an adversary can perform off-line [Brute Force](https://attack.mitre.org/techniques/T1110) cracking to gain access to plaintext credentials.(Citation: Cylance Redirect to SMB)

There are several different ways this can occur.(Citation: Osanda Stealing NetNTLM Hashes) Some specifics from in-the-wild use include:

* A spearphishing attachment containing a document with a resource that is automatically loaded when the document is opened (i.e. [Template Injection](https://attack.mitre.org/techniques/T1221)). The document can include, for example, a request similar to <code>file[:]//[remote address]/Normal.dotm</code> to trigger the SMB request.(Citation: US-CERT APT Energy Oct 2017)
* A modified .LNK or .SCF file with the icon filename pointing to an external reference such as <code>\\[remote address]\pic.png</code> that will force the system to load the resource when the icon is rendered to repeatedly gather credentials.(Citation: US-CERT APT Energy Oct 2017)

Alternatively, by leveraging the <code>EfsRpcOpenFileRaw</code> function, an adversary can send SMB requests to a remote system's MS-EFSRPC interface and force the victim computer to initiate an authentication procedure and share its authentication details. The Encrypting File System Remote Protocol (EFSRPC) is a protocol used in Windows networks for maintenance and management operations on encrypted data that is stored remotely to be accessed over a network. Utilization of <code>EfsRpcOpenFileRaw</code> function in EFSRPC is used to open an encrypted object on the server for backup or restore. Adversaries can collect this data and abuse it as part of an NTLM relay attack to gain access to remote systems on the same internal network.(Citation: Rapid7)(Citation: GitHub)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1187)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code with attempting to use PetitPotam and Printerbug as NTLM relay attacks.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G0079 - DarkHydrus](../../../Threat%20Intelligence/Groups/G0079%20-%20DarkHydrus.md) — [DarkHydrus](https://attack.mitre.org/groups/G0079) used [Template Injection](https://attack.mitre.org/techniques/T1221) to launch an authentication window for users to enter their credentials.(Citation: Unit 42 Phishery Aug 2018) [Unit 42 Phishery Aug 2018](https://researchcenter.paloaltonetworks.com/2018/08/unit42-darkhydrus-uses-phishery-harvest-credentials-middle-east/)
- [G0035 - Dragonfly](../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) has gathered hashed user credentials over SMB using spearphishing attachments with external resource links and by modifying .LNK file icon resources to collect credentials from virtualized systems.(Citation: US-CERT TA18-074A)(Citation: Gigamon Berserk Bear October 2021) [US-CERT TA18-074A](https://www.us-cert.gov/ncas/alerts/TA18-074A) · [Gigamon Berserk Bear October 2021](https://vblocalhost.com/uploads/VB2021-Slowik.pdf)
- [S0634 - EnvyScout](../../../Threat%20Intelligence/Software/Malware/S0634%20-%20EnvyScout.md) — [EnvyScout](https://attack.mitre.org/software/S0634) can use protocol handlers to coax the operating system to send NTLMv2 authentication responses to attacker-controlled infrastructure.(Citation: MSTIC Nobelium Toolset May 2021) [MSTIC Nobelium Toolset May 2021](https://www.microsoft.com/security/blog/2021/05/28/breaking-down-nobeliums-latest-early-stage-toolset/)

## Mitigations

- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Block SMB traffic from exiting an enterprise network with egress filtering or by blocking TCP ports 139, 445 and UDP port 137. Filter or block WebDAV protocol traffic from exiting the network. If access to external resources over SMB and WebDAV is necessary, then traffic should be tightly limited with allowlisting. (Citation: US-CERT SMB Security) (Citation: US-CERT APT Energy Oct 2017) [US-CERT SMB Security](https://www.us-cert.gov/ncas/current-activity/2017/01/16/SMB-Security-Best-Practices) · [US-CERT APT Energy Oct 2017](https://www.us-cert.gov/ncas/alerts/TA17-293A)
- [M1027 - Password Policies](../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Use strong passwords to increase the difficulty of credential hashes from being cracked if they are obtained.

## Detection strategies

- [DET0022 - Detect Forced SMB/WebDAV Authentication via lure files and outbound NTLM](../../../Defenses/Detection%20Strategies/DET0022%20-%20Detect%20Forced%20SMB%20-%20WebDAV%20Authentication%20via%20lure%20files%20and%20outbound%20NTLM.md)

## Sources

- [Rapid7](https://www.rapid7.com/blog/post/2021/08/03/petitpotam-novel-attack-chain-can-fully-compromise-windows-domains-running-ad-cs/)
- [Cylance Redirect to SMB](https://www.cylance.com/content/dam/cylance/pdfs/white_papers/RedirectToSMB.pdf)
- [GitHub Hashjacking](https://github.com/hob0/hashjacking)
- [Microsoft Managing WebDAV Security](https://web.archive.org/web/20100210125749/https://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/4beddb35-0cba-424c-8b9b-a5832ad8e208.mspx)
- [Osanda Stealing NetNTLM Hashes](https://osandamalith.com/2017/03/24/places-of-interest-in-stealing-netntlm-hashes/)
- [Didier Stevens WebDAV Traffic](https://blog.didierstevens.com/2017/11/13/webdav-traffic-to-malicious-sites/)
- [GitHub](https://github.com/topotam/PetitPotam)
- [US-CERT APT Energy Oct 2017](https://www.us-cert.gov/ncas/alerts/TA17-293A)
- [Wikipedia Server Message Block](https://en.wikipedia.org/wiki/Server_Message_Block)
