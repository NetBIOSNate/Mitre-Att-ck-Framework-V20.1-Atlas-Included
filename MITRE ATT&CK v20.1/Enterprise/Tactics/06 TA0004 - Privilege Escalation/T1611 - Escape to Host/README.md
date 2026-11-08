# T1611 - Escape to Host

[Enterprise](../../../README.md) / [Privilege Escalation](../README.md)

Adversaries may break out of a container or virtualized environment to gain access to the underlying host. This can allow an adversary access to other containerized or virtualized resources from the host level or to the host itself. In principle, containerized / virtualized resources should provide a clear separation of application functionality and be isolated from the host environment.(Citation: Docker Overview)

There are multiple ways an adversary may escape from a container to a host environment. Examples include creating a container configured to mount the host’s filesystem using the bind parameter, which allows the adversary to drop payloads and execute control utilities such as cron on the host; utilizing a privileged container to run commands or load a malicious kernel module on the underlying host; or abusing system calls such as `unshare` and `keyctl` to escalate privileges and steal secrets.(Citation: Docker Bind Mounts)(Citation: Trend Micro Privileged Container)(Citation: Intezer Doki July 20)(Citation: Container Escape)(Citation: Crowdstrike Kubernetes Container Escape)(Citation: Keyctl-unmask)

Additionally, an adversary may be able to exploit a compromised container with a mounted container management socket, such as `docker.sock`, to break out of the container via a [Container Administration Command](https://attack.mitre.org/techniques/T1609).(Citation: Container Escape) Adversaries may also escape via [Exploitation for Privilege Escalation](https://attack.mitre.org/techniques/T1068), such as exploiting vulnerabilities in global symbolic links in order to access the root directory of a host machine.(Citation: Windows Server Containers Are Open)

In ESXi environments, an adversary may exploit a vulnerability in order to escape from a virtual machine into the hypervisor.(Citation: Broadcom VMSA-2025-004)

Gaining access to the host may provide the adversary with the opportunity to achieve follow-on objectives, such as establishing persistence, moving laterally within the environment, accessing other containers or virtual machines running on the host, or setting up a command and control channel on the host.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1611)

**Tactics**  [Privilege Escalation](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Containers](../../../Platforms/Containers.md), [ESXi](../../../Platforms/ESXi.md)

## Procedure examples

- [S0600 - Doki](../../../Threat%20Intelligence/Software/Malware/S0600%20-%20Doki.md) — [Doki](https://attack.mitre.org/software/S0600)’s container was configured to bind the host root directory.(Citation: Intezer Doki July 20) [Intezer Doki July 20](https://www.intezer.com/blog/cloud-security/watch-your-containers-doki-infecting-docker-servers-in-the-cloud/)
- [S0601 - Hildegard](../../../Threat%20Intelligence/Software/Malware/S0601%20-%20Hildegard.md) — [Hildegard](https://attack.mitre.org/software/S0601) has used the BOtB tool that can break out of containers. (Citation: Unit 42 Hildegard Malware) [Unit 42 Hildegard Malware](https://unit42.paloaltonetworks.com/hildegard-malware-teamtnt/)
- [S0683 - Peirates](../../../Threat%20Intelligence/Software/Tools/S0683%20-%20Peirates.md) — [Peirates](https://attack.mitre.org/software/S0683) can gain a reverse shell on a host node by mounting the Kubernetes hostPath.(Citation: Peirates GitHub) [Peirates GitHub](https://github.com/inguardians/peirates)
- [S0623 - Siloscape](../../../Threat%20Intelligence/Software/Malware/S0623%20-%20Siloscape.md) — [Siloscape](https://attack.mitre.org/software/S0623) maps the host’s C drive to the container by creating a global symbolic link to the host through the calling of <code>NtSetInformationSymbolicLink</code>.(Citation: Unit 42 Siloscape Jun 2021) [Unit 42 Siloscape Jun 2021](https://unit42.paloaltonetworks.com/siloscape/)
- [G0139 - TeamTNT](../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has deployed privileged containers that mount the filesystem of victim machine.(Citation: Intezer TeamTNT September 2020)(Citation: Aqua TeamTNT August 2020) [Intezer TeamTNT September 2020](https://www.intezer.com/blog/cloud-security/attackers-abusing-legitimate-cloud-monitoring-tools-to-conduct-cyber-attacks/) · [Aqua TeamTNT August 2020](https://blog.aquasec.com/container-security-tnt-container-attack)

## Mitigations

- [M1048 - Application Isolation and Sandboxing](../../../Defenses/Mitigations/M1048%20-%20Application%20Isolation%20and%20Sandboxing.md) — Consider utilizing seccomp, seccomp-bpf, or a similar solution that restricts certain system calls such as mount. In Kubernetes environments, consider defining Pod Security Standards that limit container access to host process namespaces, the host network, and the host file system.(Citation: Kubernetes Hardening Guide) [Kubernetes Hardening Guide](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)
- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Remove unnecessary tools and software from containers.
- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use read-only containers, read-only file systems, and minimal images when possible to prevent the running of commands.(Citation: Kubernetes Hardening Guide) Where possible, also consider using application control and software restriction tools (such as those provided by SELinux) to restrict access to files, processes, and system calls in containers.(Citation: Kubernetes Security Context) [Kubernetes Security Context](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/) · [Kubernetes Hardening Guide](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Ensure containers are not running as root by default and do not use unnecessary privileges or mounted components. In Kubernetes environments, consider defining Pod Security Standards that prevent pods from running privileged containers.(Citation: Kubernetes Hardening Guide) [Kubernetes Hardening Guide](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Ensure that hosts are kept up-to-date with security patches.

## Detection strategies

- [DET0219 - Detection Strategy for Escape to Host](../../../Defenses/Detection%20Strategies/DET0219%20-%20Detection%20Strategy%20for%20Escape%20to%20Host.md)

## Sources

- [Container Escape](https://0xn3va.gitbook.io/cheat-sheets/container/escaping)
- [Broadcom VMSA-2025-004](https://github.com/vmware/vcf-security-and-compliance-guidelines/tree/main/security-advisories/vmsa-2025-0004)
- [Windows Server Containers Are Open](https://unit42.paloaltonetworks.com/windows-server-containers-vulnerabilities/)
- [Docker Overview](https://docs.docker.com/get-started/overview/)
- [Docker Bind Mounts](https://docs.docker.com/storage/bind-mounts/)
- [Trend Micro Privileged Container](https://www.trendmicro.com/en_us/research/19/l/why-running-a-privileged-container-in-docker-is-a-bad-idea.html)
- [Intezer Doki July 20](https://www.intezer.com/blog/cloud-security/watch-your-containers-doki-infecting-docker-servers-in-the-cloud/)
- [Crowdstrike Kubernetes Container Escape](https://www.crowdstrike.com/blog/cve-2022-0185-kubernetes-container-escape-using-linux-kernel-exploit/)
- [Keyctl-unmask](https://www.antitree.com/2020/07/keyctl-unmask-going-florida-on-the-state-of-containerizing-linux-keyrings/)
