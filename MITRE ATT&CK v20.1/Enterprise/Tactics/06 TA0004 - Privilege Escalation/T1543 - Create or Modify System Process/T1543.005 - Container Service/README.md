# T1543.005 - Container Service

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1543 - Create or Modify System Process](../README.md)

Adversaries may create or modify container or container cluster management tools that run as daemons, agents, or services on individual hosts. These include software for creating and managing individual containers, such as Docker and Podman, as well as container cluster node-level agents such as kubelet. By modifying these services, an adversary may be able to achieve persistence or escalate their privileges on a host.

For example, by using the `docker run` or `podman run` command with the `restart=always` directive, a container can be configured to persistently restart on the host.(Citation: AquaSec TeamTNT 2023) A user with access to the (rootful) docker command may also be able to escalate their privileges on the host.(Citation: GTFOBins Docker)

In Kubernetes environments, DaemonSets allow an adversary to persistently [Deploy Container](https://attack.mitre.org/techniques/T1610)s on all nodes, including ones added later to the cluster.(Citation: Aquasec Kubernetes Attack 2023)(Citation: Kubernetes DaemonSet) Pods can also be deployed to specific nodes using the `nodeSelector` or `nodeName` fields in the pod spec.(Citation: Kubernetes Assigning Pods to Nodes)(Citation: AppSecco Kubernetes Namespace Breakout 2020)

Note that containers can also be configured to run as [Systemd Service](https://attack.mitre.org/techniques/T1543/002)s.(Citation: Podman Systemd)(Citation: Docker Systemd)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1543/005)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md)

## Mitigations

- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Where possible, consider enforcing the use of container services in rootless mode to limit the possibility of privilege escalation or malicious effects on the host running the container.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit access to utilities such as docker to only users who have a legitimate need, especially if using docker in rootful mode. In Kubernetes environments, only grant privileges to deploy pods to users that require it.

## Detection strategies

- [DET0473 - Detect persistent or elevated container services via container runtime or cluster manipulation](../../../../Defenses/Detection%20Strategies/DET0473%20-%20Detect%20persistent%20or%20elevated%20container%20services%20via%20container%20runtime%20or%20cluster%20man.md)

## Procedure examples

- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has modified container service configurations using `Guest Shell`.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)

## Sources

- [AppSecco Kubernetes Namespace Breakout 2020](https://blog.appsecco.com/kubernetes-namespace-breakout-using-insecure-host-path-volume-part-1-b382f2a6e216)
- [Docker Systemd](https://docs.docker.com/config/containers/start-containers-automatically/)
- [GTFOBins Docker](https://gtfobins.github.io/gtfobins/docker/)
- [Kubernetes Assigning Pods to Nodes](https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/)
- [Kubernetes DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)
- [Aquasec Kubernetes Attack 2023](https://blog.aquasec.com/leveraging-kubernetes-rbac-to-backdoor-clusters)
- [AquaSec TeamTNT 2023](https://blog.aquasec.com/teamtnt-reemerged-with-new-aggressive-cloud-campaign)
- [Podman Systemd](https://www.redhat.com/sysadmin/podman-run-pods-systemd-services)
