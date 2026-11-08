# T1613 - Container and Resource Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to discover containers and other resources that are available within a containers environment. Other resources may include images, deployments, pods, nodes, and other information such as the status of a cluster.

These resources can be viewed within web applications such as the Kubernetes dashboard or can be queried via the Docker and Kubernetes APIs.(Citation: Docker API)(Citation: Kubernetes API) In Docker, logs may leak information about the environment, such as the environment’s configuration, which services are available, and what cloud provider the victim may be utilizing. The discovery of these resources may inform an adversary’s next steps in the environment, such as how to perform lateral movement and which methods to utilize for execution.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1613)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Containers](../../../Platforms/Containers.md)

## Procedure examples

- [S9042 - CanisterWorm](../../../Threat%20Intelligence/Software/Malware/S9042%20-%20CanisterWorm.md) — [CanisterWorm](https://attack.mitre.org/software/S9042) has performed environment fingerprinting to identify Kubernetes clusters.(Citation: Palo Alto TeamPCP MAR 2026) [CanisterWorm](https://attack.mitre.org/software/S9042) has also searched for Kubernetes pods using the command ` os.path.exists("/var/run/secrets/kubernetes.io/serviceaccount") or "KUBERNETES_SERVICE_HOST" in os.environ `.(Citation: Aikido CanisterWorm MAR 2026) [Aikido CanisterWorm MAR 2026](https://www.aikido.dev/blog/teampcp-stage-payload-canisterworm-iran) · [Palo Alto TeamPCP MAR 2026](https://unit42.paloaltonetworks.com/teampcp-supply-chain-attacks/)
- [S0601 - Hildegard](../../../Threat%20Intelligence/Software/Malware/S0601%20-%20Hildegard.md) — [Hildegard](https://attack.mitre.org/software/S0601) has used masscan to search for kubelets and the kubelet API for additional running containers.(Citation: Unit 42 Hildegard Malware) [Unit 42 Hildegard Malware](https://unit42.paloaltonetworks.com/hildegard-malware-teamtnt/)
- [S0683 - Peirates](../../../Threat%20Intelligence/Software/Tools/S0683%20-%20Peirates.md) — [Peirates](https://attack.mitre.org/software/S0683) can enumerate Kubernetes pods in a given namespace.(Citation: Peirates GitHub) [Peirates GitHub](https://github.com/inguardians/peirates)
- [S9041 - TeamPCP Cloud Stealer](../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can identify Docker and Kubernetes environments for credentials.(Citation: Aqua Security Blog Trivy Compromise APR 2026)(Citation: Wiz TeamPCP KICS MAR 2026) [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know) · [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action)
- [G0139 - TeamTNT](../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has checked for running containers with <code>docker ps</code> and for specific container names with <code>docker inspect</code>.(Citation: Trend Micro TeamTNT) [TeamTNT](https://attack.mitre.org/groups/G0139) has also searched for Kubernetes pods running in a local network.(Citation: Cisco Talos Intelligence Group) [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/) · [Trend Micro TeamTNT](https://documents.trendmicro.com/assets/white_papers/wp-tracking-the-activities-of-teamTNT.pdf)

## Mitigations

- [M1035 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Limit communications with the container service to managed and secured channels, such as local Unix sockets or remote access via SSH. Require secure port access to communicate with the APIs over TLS by disabling unauthenticated access to the Docker API and Kubernetes API Server.(Citation: Docker Daemon Socket Protect)(Citation: Kubernetes API Control Access) In Kubernetes clusters deployed in cloud environments, use native cloud platform features to restrict the IP ranges that are permitted to access to API server.(Citation: Kubernetes Cloud Native Security) Where possible, consider enabling just-in-time (JIT) access to the Kubernetes API to place additional restrictions on access.(Citation: Microsoft AKS Azure AD 2023) [Docker Daemon Socket Protect](https://docs.docker.com/engine/security/protect-access/) · [Kubernetes Cloud Native Security](https://kubernetes.io/docs/concepts/security/overview/) · [Microsoft AKS Azure AD 2023](https://learn.microsoft.com/en-us/azure/aks/managed-aad) · [Kubernetes API Control Access](https://kubernetes.io/docs/concepts/security/controlling-access/)
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Deny direct remote access to internal systems through the use of network proxies, gateways, and firewalls.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least privilege by limiting dashboard visibility to only the required users. When using Kubernetes, avoid giving users wildcard permissions or adding users to the `system:masters` group, and use `RoleBindings` rather than `ClusterRoleBindings` to limit user privileges to specific namespaces.(Citation: Kubernetes RBAC) [Kubernetes RBAC](https://kubernetes.io/docs/concepts/security/rbac-good-practices/)

## Detection strategies

- [DET0490 - Detection Strategy for Container and Resource Discovery](../../../Defenses/Detection%20Strategies/DET0490%20-%20Detection%20Strategy%20for%20Container%20and%20Resource%20Discovery.md)

## Sources

- [Docker API](https://docs.docker.com/engine/api/v1.41/)
- [Kubernetes API](https://kubernetes.io/docs/concepts/overview/kubernetes-api/)
