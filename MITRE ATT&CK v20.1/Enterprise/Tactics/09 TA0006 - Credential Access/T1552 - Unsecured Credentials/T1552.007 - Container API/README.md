# T1552.007 - Container API

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1552 - Unsecured Credentials](../README.md)

Adversaries may gather credentials via APIs within a containers environment. APIs in these environments, such as the Docker API and Kubernetes APIs, allow a user to remotely manage their container resources and cluster components.(Citation: Docker API)(Citation: Kubernetes API)

An adversary may access the Docker API to collect logs that contain credentials to cloud, container, and various other resources in the environment.(Citation: Unit 42 Unsecured Docker Daemons) An adversary with sufficient permissions, such as via a pod's service account, may also use the Kubernetes API to retrieve credentials from the Kubernetes API server. These credentials may include those needed for Docker API authentication or secrets from Kubernetes cluster components.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1552/007)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md)

## Detection strategies

- [DET0198 - Detect Abuse of Container APIs for Credential Access](../../../../Defenses/Detection%20Strategies/DET0198%20-%20Detect%20Abuse%20of%20Container%20APIs%20for%20Credential%20Access.md)

## Procedure examples

- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has gathered unsecured API keys stored in container orchestrators.(Citation: Hunt.io TeamPCP Toolkit MAY 2026) [Hunt.io TeamPCP Toolkit MAY 2026](https://hunt.io/blog/teampcp-python-toolkit-firescale-github-c2-takedown)
- [S0683 - Peirates](../../../../Threat%20Intelligence/Software/Tools/S0683%20-%20Peirates.md) — [Peirates](https://attack.mitre.org/software/S0683) can query the Kubernetes API for secrets.(Citation: Peirates GitHub) [Peirates GitHub](https://github.com/inguardians/peirates)
- [S9041 - TeamPCP Cloud Stealer](../../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can query the Kubernetes API for credentials.(Citation: Wiz TeamPCP KICS MAR 2026)(Citation: Palo Alto TeamPCP MAR 2026) [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action) · [Palo Alto TeamPCP MAR 2026](https://unit42.paloaltonetworks.com/teampcp-supply-chain-attacks/)

## Mitigations

- [M1035 - Limit Access to Resource Over Network](../../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Limit communications with the container service to managed and secured channels, such as local Unix sockets or remote access via SSH. Require secure port access to communicate with the APIs over TLS by disabling unauthenticated access to the Docker API and Kubernetes API Server.(Citation: Docker Daemon Socket Protect)(Citation: Kubernetes API Control Access) In Kubernetes clusters deployed in cloud environments, use native cloud platform features to restrict the IP ranges that are permitted to access to API server.(Citation: Kubernetes Cloud Native Security) Where possible, consider enabling just-in-time (JIT) access to the Kubernetes API to place additional restrictions on access.(Citation: Microsoft AKS Azure AD 2023) [Docker Daemon Socket Protect](https://docs.docker.com/engine/security/protect-access/) · [Kubernetes Cloud Native Security](https://kubernetes.io/docs/concepts/security/overview/) · [Microsoft AKS Azure AD 2023](https://learn.microsoft.com/en-us/azure/aks/managed-aad) · [Kubernetes API Control Access](https://kubernetes.io/docs/concepts/security/controlling-access/)
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Deny direct remote access to internal systems through the use of network proxies, gateways, and firewalls.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Use the principle of least privilege for privileged accounts such as the service account in Kubernetes. For example, if a pod is not required to access the Kubernetes API, consider disabling the service account altogether.(Citation: Kubernetes Service Accounts) [Kubernetes Service Accounts](https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce authentication and role-based access control on the container API to restrict users to the least privileges required.(Citation: Kubernetes Hardening Guide) When using Kubernetes, avoid giving users wildcard permissions or adding users to the `system:masters` group, and use `RoleBindings` rather than `ClusterRoleBindings` to limit user privileges to specific namespaces.(Citation: Kubernetes RBAC) [Kubernetes RBAC](https://kubernetes.io/docs/concepts/security/rbac-good-practices/) · [Kubernetes Hardening Guide](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)

## Sources

- [Unit 42 Unsecured Docker Daemons](https://unit42.paloaltonetworks.com/attackers-tactics-and-techniques-in-unsecured-docker-daemons-revealed/)
- [Docker API](https://docs.docker.com/engine/api/v1.41/)
- [Kubernetes API](https://kubernetes.io/docs/concepts/overview/kubernetes-api/)
