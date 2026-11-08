# T1610 - Deploy Container

[Enterprise](../../../README.md) / [Execution](../README.md)

Adversaries may deploy a container into an environment to facilitate execution or evade defenses. In some cases, adversaries may deploy a new container to execute processes associated with a particular image or deployment, such as processes that execute or download malware. In others, an adversary may deploy a new container configured without network rules, user limitations, etc. to bypass existing defenses within the environment. In Kubernetes environments, an adversary may attempt to deploy a privileged or vulnerable container into a specific node in order to [Escape to Host](https://attack.mitre.org/techniques/T1611) and access other containers running on the node.(Citation: AppSecco Kubernetes Namespace Breakout 2020)

Containers can be deployed by various means, such as via Docker's <code>create</code> and <code>start</code> APIs or via a web application such as the Kubernetes dashboard or Kubeflow.(Citation: Docker Container)(Citation: Kubernetes Dashboard)(Citation: Kubeflow Pipelines) In Kubernetes environments, containers may be deployed through workloads such as ReplicaSets or DaemonSets, which can allow containers to be deployed across multiple nodes.(Citation: Kubernetes Workload Management) Adversaries may deploy containers based on retrieved or built malicious images or from benign images that download and execute malicious payloads at runtime.(Citation: Aqua Build Images on Hosts)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1610)

**Tactics**  [Execution](../README.md)

**Platforms**  [Containers](../../../Platforms/Containers.md)

## Procedure examples

- [S0600 - Doki](../../../Threat%20Intelligence/Software/Malware/S0600%20-%20Doki.md) — [Doki](https://attack.mitre.org/software/S0600) was run through a deployed container.(Citation: Intezer Doki July 20) [Intezer Doki July 20](https://www.intezer.com/blog/cloud-security/watch-your-containers-doki-infecting-docker-servers-in-the-cloud/)
- [S0599 - Kinsing](../../../Threat%20Intelligence/Software/Malware/S0599%20-%20Kinsing.md) — [Kinsing](https://attack.mitre.org/software/S0599) was run through a deployed Ubuntu container.(Citation: Aqua Kinsing April 2020) [Aqua Kinsing April 2020](https://blog.aquasec.com/threat-alert-kinsing-malware-container-vulnerability)
- [S0683 - Peirates](../../../Threat%20Intelligence/Software/Tools/S0683%20-%20Peirates.md) — [Peirates](https://attack.mitre.org/software/S0683) can deploy a pod that mounts its node’s root file system, then execute a command to create a reverse shell on the node.(Citation: Peirates GitHub) [Peirates GitHub](https://github.com/inguardians/peirates)
- [G1045 - Salt Typhoon](../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has enabled Linux containers in victim network device environments using `guestshell enable`.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)
- [G1056 - TeamPCP](../../../Threat%20Intelligence/Groups/G1056%20-%20TeamPCP.md) — [TeamPCP](https://attack.mitre.org/groups/G1056) has deployed privileged DaemonSets to delete files on targeted Kubernetes clusters.(Citation: Palo Alto TeamPCP MAR 2026) [Palo Alto TeamPCP MAR 2026](https://unit42.paloaltonetworks.com/teampcp-supply-chain-attacks/)
- [S9041 - TeamPCP Cloud Stealer](../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can deploy a pod in Kubernetes containers to run a script to establish persistence.(Citation: Wiz TeamPCP KICS MAR 2026) [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action)
- [G0139 - TeamTNT](../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has deployed different types of containers into victim environments to facilitate execution.(Citation: Intezer TeamTNT September 2020)(Citation: Trend Micro TeamTNT) [TeamTNT](https://attack.mitre.org/groups/G0139) has also transferred cryptocurrency mining software to Kubernetes clusters discovered within local IP address ranges.(Citation: Cisco Talos Intelligence Group) [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/) · [Trend Micro TeamTNT](https://documents.trendmicro.com/assets/white_papers/wp-tracking-the-activities-of-teamTNT.pdf) · [Intezer TeamTNT September 2020](https://www.intezer.com/blog/cloud-security/attackers-abusing-legitimate-cloud-monitoring-tools-to-conduct-cyber-attacks/)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Scan images before deployment, and block those that are not in compliance with security policies. In Kubernetes environments, the admission controller can be used to validate images after a container deployment request is authenticated but before the container is deployed.(Citation: Kubernetes Hardening Guide) [Kubernetes Hardening Guide](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)
- [M1035 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Limit communications with the container service to managed and secured channels, such as local Unix sockets or remote access via SSH. Require secure port access to communicate with the APIs over TLS by disabling unauthenticated access to the Docker API, Kubernetes API Server, and container orchestration web applications.(Citation: Docker Daemon Socket Protect)(Citation: Kubernetes API Control Access) In Kubernetes clusters deployed in cloud environments, use native cloud platform features to restrict the IP ranges that are permitted to access to API server.(Citation: Kubernetes Cloud Native Security) Where possible, consider enabling just-in-time (JIT) access to the Kubernetes API to place additional restrictions on access.(Citation: Microsoft AKS Azure AD 2023) [Docker Daemon Socket Protect](https://docs.docker.com/engine/security/protect-access/) · [Kubernetes Cloud Native Security](https://kubernetes.io/docs/concepts/security/overview/) · [Microsoft AKS Azure AD 2023](https://learn.microsoft.com/en-us/azure/aks/managed-aad) · [Kubernetes API Control Access](https://kubernetes.io/docs/concepts/security/controlling-access/)
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Deny direct remote access to internal systems through the use of network proxies, gateways, and firewalls.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least privilege by limiting container dashboard access to only the necessary users. When using Kubernetes, avoid giving users wildcard permissions or adding users to the `system:masters` group, and use `RoleBindings` rather than `ClusterRoleBindings` to limit user privileges to specific namespaces.(Citation: Kubernetes RBAC) [Kubernetes RBAC](https://kubernetes.io/docs/concepts/security/rbac-good-practices/)

## Detection strategies

- [DET0249 - Behavior-chain detection for T1610 Deploy Container across Docker & Kubernetes control/node planes](../../../Defenses/Detection%20Strategies/DET0249%20-%20Behavior-chain%20detection%20for%20T1610%20Deploy%20Container%20across%20Docker%20%26%20Kubernetes%20contro.md)

## Sources

- [AppSecco Kubernetes Namespace Breakout 2020](https://blog.appsecco.com/kubernetes-namespace-breakout-using-insecure-host-path-volume-part-1-b382f2a6e216)
- [Aqua Build Images on Hosts](https://blog.aquasec.com/malicious-container-image-docker-container-host)
- [Docker Container](https://docs.docker.com/reference/cli/docker/container/create/)
- [Kubernetes Workload Management](https://kubernetes.io/docs/concepts/workloads/controllers/)
- [Kubeflow Pipelines](https://www.kubeflow.org/docs/components/pipelines/overview/pipelines-overview/)
- [Kubernetes Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)
