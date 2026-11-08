# T1537 - Transfer Data to Cloud Account

[Enterprise](../../../README.md) / [Exfiltration](../README.md)

Adversaries may exfiltrate data by transferring the data, including through sharing/syncing and creating backups of cloud environments, to another cloud account they control on the same service.

A defender who is monitoring for large transfers to outside the cloud environment through normal file transfers or over command and control channels may not be watching for data transfers to another account within the same cloud provider. Such transfers may utilize existing cloud provider APIs and the internal address space of the cloud provider to blend into normal traffic or avoid data transfers over external network interfaces.(Citation: TLDRSec AWS Attacks)

Adversaries may also use cloud-native mechanisms to share victim data with adversary-controlled cloud accounts, such as creating anonymous file sharing links or, in Azure, a shared access signature (SAS) URI.(Citation: Microsoft Azure Storage Shared Access Signature)

Incidents have been observed where adversaries have created backups of cloud instances and transferred them to separate accounts.(Citation: DOJ GRU Indictment Jul 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1537)

**Tactics**  [Exfiltration](../README.md)

**Platforms**  [IaaS](../../../Platforms/IaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md)

## Procedure examples

- [G1032 - INC Ransom](../../../Threat%20Intelligence/Groups/G1032%20-%20INC%20Ransom.md) — [INC Ransom](https://attack.mitre.org/groups/G1032) has used Megasync to exfiltrate data to the cloud.(Citation: Secureworks GOLD IONIC April 2024) [Secureworks GOLD IONIC April 2024](https://www.secureworks.com/blog/gold-ionic-deploys-inc-ransomware)
- [G1039 - RedCurl](../../../Threat%20Intelligence/Groups/G1039%20-%20RedCurl.md) — [RedCurl](https://attack.mitre.org/groups/G1039) has used cloud storage to exfiltrate data, in particular the megatools utilities were used to exfiltrate data to Mega, a file storage service.(Citation: group-ib_redcurl1)(Citation: group-ib_redcurl2) [group-ib_redcurl1](https://www.group-ib.com/resources/research-hub/red-curl/) · [group-ib_redcurl2](https://www.group-ib.com/resources/research-hub/red-curl-2/)
- [G1053 - Storm-0501](../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has copied data from the victims environment to their own infrastructure leveraging AzCopy CLI.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)

## Mitigations

- [M1057 - Data Loss Prevention](../../../Defenses/Mitigations/M1057%20-%20Data%20Loss%20Prevention.md) — Data loss prevention can prevent and block sensitive data from being shared with individuals outside an organization.(Citation: Microsoft Purview Data Loss Prevention) (Citation: Google Workspace Data Loss Prevention) [Google Workspace Data Loss Prevention](https://support.google.com/a/answer/9646351) · [Microsoft Purview Data Loss Prevention](https://learn.microsoft.com/en-us/purview/dlp-learn-about-dlp)
- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Implement network-based filtering restrictions to prohibit data transfers to untrusted VPCs.
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Configure appropriate data sharing restrictions in cloud services. For example, external sharing in Microsoft SharePoint and Google Drive can be turned off altogether, blocked for certain domains, or restricted to certain users.(Citation: Google Workspace External Sharing) (Citation: Microsoft 365 External Sharing) [Google Workspace External Sharing](https://support.google.com/a/answer/60781) · [Microsoft 365 External Sharing](https://learn.microsoft.com/en-us/sharepoint/turn-external-sharing-on-or-off)
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit user account and IAM policies to the least privileges required.

## Detection strategies

- [DET0573 - Cross-Platform Detection of Data Transfer to Cloud Account](../../../Defenses/Detection%20Strategies/DET0573%20-%20Cross-Platform%20Detection%20of%20Data%20Transfer%20to%20Cloud%20Account.md)

## Sources

- [AWS EBS Snapshot Sharing](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-modifying-snapshot-permissions.html)
- [TLDRSec AWS Attacks](https://tldrsec.com/p/blog-lesser-known-aws-attacks)
- [Azure Shared Access Signature](https://docs.microsoft.com/en-us/rest/api/storageservices/delegate-access-with-shared-access-signature)
- [Azure Blob Snapshots](https://docs.microsoft.com/en-us/azure/storage/blobs/snapshots-overview)
- [Microsoft Azure Storage Shared Access Signature](https://learn.microsoft.com/en-us/azure/storage/common/storage-sas-overview)
- [DOJ GRU Indictment Jul 2018](https://cdn.cnn.com/cnn/2018/images/07/13/gru.indictment.pdf)
