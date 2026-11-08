# DC0083 - Cloud Service Enumeration

[Enterprise](../../README.md) / [Data Components](README.md)

Cloud service enumeration involves listing or querying available cloud services in a cloud control plane. This activity is often performed to identify resources such as virtual machines, storage buckets, compute clusters, or other services within a cloud environment. Examples include API calls like `AWS ECS ListServices`, `Azure ListAllResources`, or `Google Cloud ListInstances`. Examples: 

AWS Cloud Service Enumeration: The adversary gathers details about existing ECS services to identify opportunities for privilege escalation or exfiltration.
- Azure Resource Enumeration: The adversary collects information about virtual machines, resource groups, and other Azure assets for reconnaissance purposes.
- Google Cloud Resource Enumeration: The attacker seeks to map the environment and find misconfigured or underutilized resources for exploitation.
- Office 365 Service Enumeration: The attacker may look for data repositories or collaboration tools to exfiltrate sensitive information.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0083)

## Log sources and channels

- **AWS:CloudTrail** — GetSecretValue
- **gcp:secrets** — accessSecretVersion
- **azure:ad** — SecretGet
- **AWS:CloudTrail** — ssm:ListInventoryEntries
- **AWS:CloudTrail** — DescribeInstances, DescribeServices, ListFunctions: High frequency enumeration calls or unusual user agents performing discovery
- **azure:audit** — ListApplications, ListServicePrincipals: Large-scale queries against identity or application objects
- **m365:unified** — Get-MsolServicePrincipal, ListAppRoles: Service discovery operations executed by accounts not normally performing administrative tasks
- **saas:adminapi** — ListIntegrations, ListServices: Repeated service discovery requests from accounts without administrative responsibilities
- **AWS:CloudTrail** — GetInstanceIdentityDocument or IMDSv2 token requests
- **AWS:CloudTrail** — DescribeUsers / ListUsers / GetUser
- **azure:signinlogs** — Graph API Query
- **saas:MDM** — Device lookup, location query, or remote management operation
- **cloud:AuditLog** — Instrumented app API trace and corresponding cloud-service audit/API telemetry

## Analytics using this component

- [AN0366 - Analytic 0366](../Analytics/AN0366.md)
- [AN1103 - Analytic 1103](../Analytics/AN1103.md)
- [AN1127 - Analytic 1127](../Analytics/AN1127.md)
- [AN1128 - Analytic 1128](../Analytics/AN1128.md)
- [AN1129 - Analytic 1129](../Analytics/AN1129.md)
- [AN1130 - Analytic 1130](../Analytics/AN1130.md)
- [AN1201 - Analytic 1201](../Analytics/AN1201.md)
- [AN1424 - Analytic 1424](../Analytics/AN1424.md)
- [AN1615 - Analytic 1615](../Analytics/AN1615.md)
- [AN1616 - Analytic 1616](../Analytics/AN1616.md)
