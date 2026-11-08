# T1098.006 - Additional Container Cluster Roles

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1098 - Account Manipulation](../README.md)

An adversary may add additional roles or permissions to an adversary-controlled user or service account to maintain persistent access to a container orchestration system. For example, an adversary with sufficient permissions may create a RoleBinding or a ClusterRoleBinding to bind a Role or ClusterRole to a Kubernetes account.(Citation: Kubernetes RBAC)(Citation: Aquasec Kubernetes Attack 2023) Where attribute-based access control (ABAC) is in use, an adversary with sufficient permissions may modify a Kubernetes ABAC policy to give the target account additional permissions.(Citation: Kuberentes ABAC)
 
This account modification may immediately follow [Create Account](https://attack.mitre.org/techniques/T1136) or other malicious account activity. Adversaries may also modify existing [Valid Accounts](https://attack.mitre.org/techniques/T1078) that they have compromised.  

Note that where container orchestration systems are deployed in cloud environments, as with Google Kubernetes Engine, Amazon Elastic Kubernetes Service, and Azure Kubernetes Service, cloud-based  role-based access control (RBAC) assignments or ABAC policies can often be used in place of or in addition to local permission assignments.(Citation: Google Cloud Kubernetes IAM)(Citation: AWS EKS IAM Roles for Service Accounts)(Citation: Microsoft Azure Kubernetes Service Service Accounts) In these cases, this technique may be used in conjunction with [Additional Cloud Roles](https://attack.mitre.org/techniques/T1098/003).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1098/006)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md)

## Detection strategies

- [DET0572 - Suspicious RoleBinding or ClusterRoleBinding Assignment in Kubernetes](../../../../Defenses/Detection%20Strategies/DET0572%20-%20Suspicious%20RoleBinding%20or%20ClusterRoleBinding%20Assignment%20in%20Kubernetes.md)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Require multi-factor authentication for user accounts integrated into container clusters through cloud deployments or via authentication protocols such as LDAP or SAML.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure that low-privileged accounts do not have permissions to add permissions to accounts or to update container cluster roles.

## Sources

- [AWS EKS IAM Roles for Service Accounts](https://docs.aws.amazon.com/eks/latest/userguide/iam-roles-for-service-accounts.html)
- [Google Cloud Kubernetes IAM](https://cloud.google.com/kubernetes-engine/docs/how-to/iam)
- [Kuberentes ABAC](https://kubernetes.io/docs/reference/access-authn-authz/abac/)
- [Kubernetes RBAC](https://kubernetes.io/docs/concepts/security/rbac-good-practices/)
- [Aquasec Kubernetes Attack 2023](https://blog.aquasec.com/leveraging-kubernetes-rbac-to-backdoor-clusters)
- [Microsoft Azure Kubernetes Service Service Accounts](https://learn.microsoft.com/en-us/azure/aks/concepts-identity)
