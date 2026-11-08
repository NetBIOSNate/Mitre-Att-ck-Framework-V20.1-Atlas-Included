# T1053.007 - Container Orchestration Job

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1053 - Scheduled Task/Job](../README.md)

Adversaries may abuse task scheduling functionality provided by container orchestration tools such as Kubernetes to schedule deployment of containers configured to execute malicious code. Container orchestration jobs run these automated tasks at a specific date and time, similar to cron jobs on a Linux system. Deployments of this type can also be configured to maintain a quantity of containers over time, automating the process of maintaining persistence within a cluster.

In Kubernetes, a CronJob may be used to schedule a Job that runs one or more containers to perform specific tasks.(Citation: Kubernetes Jobs)(Citation: Kubernetes CronJob) An adversary therefore may utilize a CronJob to schedule deployment of a Job that executes malicious code in various nodes within a cluster.(Citation: Threat Matrix for Kubernetes)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1053/007)

**Tactics**  [Execution](../../../04%20TA0002%20-%20Execution/README.md), [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md)

## Mitigations

- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Ensure containers are not running as root by default. In Kubernetes environments, consider defining Pod Security Standards that prevent pods from running privileged containers.(Citation: Kubernetes Hardening Guide) [Kubernetes Hardening Guide](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit privileges of user accounts and remediate privilege escalation vectors so only authorized administrators can create container orchestration jobs.

## Detection strategies

- [DET0206 - Detection of Malicious Kubernetes CronJob Scheduling](../../../../Defenses/Detection%20Strategies/DET0206%20-%20Detection%20of%20Malicious%20Kubernetes%20CronJob%20Scheduling.md)

## Sources

- [Kubernetes CronJob](https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/)
- [Kubernetes Jobs](https://kubernetes.io/docs/concepts/workloads/controllers/job/)
- [Threat Matrix for Kubernetes](https://www.microsoft.com/security/blog/2020/04/02/attack-matrix-kubernetes/)
