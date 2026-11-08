# T1619 - Cloud Storage Object Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

Adversaries may enumerate objects in cloud storage infrastructure. Adversaries may use this information during automated discovery to shape follow-on behaviors, including requesting all or specific objects from cloud storage.  Similar to [File and Directory Discovery](https://attack.mitre.org/techniques/T1083) on a local host, after identifying available storage services (i.e. [Cloud Infrastructure Discovery](https://attack.mitre.org/techniques/T1580)) adversaries may access the contents/objects stored in cloud infrastructure.

Cloud service providers offer APIs allowing users to enumerate objects stored within cloud storage. Examples include ListObjectsV2 in AWS(Citation: ListObjectsV2) and List Blobs in Azure.(Citation: List Blobs)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1619)

**Tactics**  [Discovery](../README.md)

**Platforms**  [IaaS](../../../Platforms/IaaS.md)

## Mitigations

- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Restrict granting of permissions related to listing objects in cloud storage to necessary accounts.

## Procedure examples

- [S1091 - Pacu](../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can enumerate AWS storage services, such as S3 buckets and Elastic Block Store volumes.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [S0683 - Peirates](../../../Threat%20Intelligence/Software/Tools/S0683%20-%20Peirates.md) — [Peirates](https://attack.mitre.org/software/S0683) can list AWS S3 buckets.(Citation: Peirates GitHub) [Peirates GitHub](https://github.com/inguardians/peirates)
- [G1057 - ShinyHunters](../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has used Amazon Simple Storage Service (S3) Browser and WinSCP to access S3 objects.(Citation: Unit42KelleyVaya_BlingLibra_Aug2024) [Unit42KelleyVaya_BlingLibra_Aug2024](https://unit42.paloaltonetworks.com/shinyhunters-ransomware-extortion/)
- [S9009 - TruffleHog](../../../Threat%20Intelligence/Software/Tools/S9009%20-%20TruffleHog.md) — [TruffleHog](https://attack.mitre.org/software/S9009) can enumerate cloud storage environments including Amazon Web Service (AWS) S3 buckets and Google Cloud Storage buckets.(Citation: Black Hills Information Security TruffleHog January 2024)(Citation: Github TruffleSecurity Trufflehog April 2025) [Black Hills Information Security TruffleHog January 2024](https://www.blackhillsinfosec.com/rooting-for-secrets-with-trufflehog/) · [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)

## Detection strategies

- [DET0578 - Detection Strategy for Cloud Storage Object Discovery](../../../Defenses/Detection%20Strategies/DET0578%20-%20Detection%20Strategy%20for%20Cloud%20Storage%20Object%20Discovery.md)

## Sources

- [ListObjectsV2](https://docs.aws.amazon.com/AmazonS3/latest/API/API_ListObjectsV2.html)
- [List Blobs](https://docs.microsoft.com/en-us/rest/api/storageservices/list-blobs)
