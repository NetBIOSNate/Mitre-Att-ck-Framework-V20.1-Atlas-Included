# T1485.001 - Lifecycle-Triggered Deletion

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1485 - Data Destruction](../README.md)

Adversaries may modify the lifecycle policies of a cloud storage bucket to destroy all objects stored within.  

Cloud storage buckets often allow users to set lifecycle policies to automate the migration, archival, or deletion of objects after a set period of time.(Citation: AWS Storage Lifecycles)(Citation: GCP Storage Lifecycles)(Citation: Azure Storage Lifecycles) If a threat actor has sufficient permissions to modify these policies, they may be able to delete all objects at once. 

For example, in AWS environments, an adversary with the `PutLifecycleConfiguration` permission may use the `PutBucketLifecycle` API call to apply a lifecycle policy to an S3 bucket that deletes all objects in the bucket after one day.(Citation: Palo Alto Cloud Ransomware)(Citation: Halcyon AWS Ransomware 2025) In addition to destroying data for purposes of extortion and [Financial Theft](https://attack.mitre.org/techniques/T1657), adversaries may also perform this action on buckets storing cloud logs for [Indicator Removal](https://attack.mitre.org/techniques/T1070).(Citation: Datadog S3 Lifecycle CloudTrail Logs)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1485/001)

**Tactics**  [Impact](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md)

## Mitigations

- [M1053 - Data Backup](../../../../Defenses/Mitigations/M1053%20-%20Data%20Backup.md) — Consider implementing IT disaster recovery plans that contain procedures for taking regular data backups that can be used to restore organizational data.(Citation: Ready.gov IT DRP) Ensure backups are stored off system and protected from common methods adversaries may use to gain access and destroy the backups to prevent recovery. [Ready.gov IT DRP](https://www.ready.gov/business/implementation/IT)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — In cloud environments, limit permissions to modify cloud bucket lifecycle policies (e.g., `PutLifecycleConfiguration` in AWS) to only those accounts that require it. In AWS environments, consider using Service Control policies to limit the use of the `PutBucketLifecycle` API call.

## Detection strategies

- [DET0041 - Detection of Lifecycle Policy Modifications for Triggered Deletion in IaaS Cloud Storage](../../../../Defenses/Detection%20Strategies/DET0041%20-%20Detection%20of%20Lifecycle%20Policy%20Modifications%20for%20Triggered%20Deletion%20in%20IaaS%20Cloud%20Stor.md)

## Sources

- [AWS Storage Lifecycles](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html)
- [GCP Storage Lifecycles](https://cloud.google.com/storage/docs/lifecycle)
- [Halcyon AWS Ransomware 2025](https://www.halcyon.ai/blog/abusing-aws-native-services-ransomware-encrypting-s3-buckets-with-sse-c)
- [Azure Storage Lifecycles](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-policy-configure?tabs=azure-portal)
- [Palo Alto Cloud Ransomware](https://www.paloaltonetworks.com/blog/prisma-cloud/ransomware-data-protection-cloud/)
- [Datadog S3 Lifecycle CloudTrail Logs](https://stratus-red-team.cloud/attack-techniques/AWS/aws.defense-evasion.cloudtrail-lifecycle-rule/)
