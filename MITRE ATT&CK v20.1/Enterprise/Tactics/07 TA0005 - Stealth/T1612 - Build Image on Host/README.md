# T1612 - Build Image on Host

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may build a container image directly on a host to bypass defenses that monitor for the retrieval of malicious images from a public registry. A remote <code>build</code> request may be sent to the Docker API that includes a Dockerfile that pulls a vanilla base image, such as alpine, from a public or local registry and then builds a custom image upon it.(Citation: Docker Build Image)

An adversary may take advantage of that <code>build</code> API to build a custom image on the host that includes malware downloaded from their C2 server, and then they may utilize [Deploy Container](https://attack.mitre.org/techniques/T1610) using that custom image.(Citation: Aqua Build Images on Hosts)(Citation: Aqua Security Cloud Native Threat Report June 2021) If the base image is pulled from a public registry, defenses will likely not detect the image as malicious since it’s a vanilla image. If the base image already resides in a local registry, the pull may be considered even less suspicious since the image is already in the environment.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1612)

**Tactics**  [Stealth](../README.md)

**Platforms**  [Containers](../../../Platforms/Containers.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Audit images deployed within the environment to ensure they do not contain any malicious components.
- [M1035 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Limit communications with the container service to local Unix sockets or remote access via SSH. Require secure port access to communicate with the APIs over TLS by disabling unauthenticated access to the Docker API on port 2375. Instead, communicate with the Docker API over TLS on port 2376.(Citation: Docker Daemon Socket Protect) [Docker Daemon Socket Protect](https://docs.docker.com/engine/security/protect-access/)
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Deny direct remote access to internal systems through the use of network proxies, gateways, and firewalls.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Ensure containers are not running as root by default. In Kubernetes environments, consider defining Pod Security Standards that prevent pods from running privileged containers.(Citation: Kubernetes Hardening Guide) [Kubernetes Hardening Guide](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)

## Detection strategies

- [DET0459 - Detection Strategy for Build Image on Host](../../../Defenses/Detection%20Strategies/DET0459%20-%20Detection%20Strategy%20for%20Build%20Image%20on%20Host.md)

## Sources

- [Aqua Build Images on Hosts](https://blog.aquasec.com/malicious-container-image-docker-container-host)
- [Docker Build Image](https://docs.docker.com/engine/api/v1.41/#operation/ImageBuild)
- [Aqua Security Cloud Native Threat Report June 2021](https://web.archive.org/web/20220106180157/https://info.aquasec.com/hubfs/Threat%20reports/AquaSecurity_Cloud_Native_Threat_Report_2021.pdf)
