# T1059.013 - Container CLI/API

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1059 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse built-in CLI tools or API calls to execute malicious commands in containerized environments.

The Docker CLI is used for managing containers via an exposed API point from the `dockerd` daemon. Some common examples of Docker CLI include Docker Desktop CLI and Docker Compose, but users are also able to use SDKs to interact with the API. For example, Docker SDK for Python can be used to run commands within a Python application.(Citation: Docker Desktop CLI)

Adversaries may leverage the Docker CLI, API, or SDK to pull or build Docker images (i.e., [Ingress Tool Transfer](https://attack.mitre.org/techniques/T1105), [Build Image on Host](https://attack.mitre.org/techniques/T1612)), run containers (i.e., [Deploy Container](https://attack.mitre.org/techniques/T1610)), or execute commands inside running containers (i.e., [Container Administration Command](https://attack.mitre.org/techniques/T1609)). In some cases, threat actors may pull legitimate images that include scripts or tools that they can leverage - for example, using an image that includes the `curl` command to download payloads.(Citation: Intezer) Adversaries may also utilize `docker inspect` and `docker ps` to scan for cloud environment variables and other running containers (i.e., [Container and Resource Discovery](https://attack.mitre.org/techniques/T1613)).(Citation: Cisco Talos Blog)(Citation: aquasec)

Kubernetes is responsible for the management and orchestration of containers across clusters. The Kubernetes control plane, which manages the state of the cluster and is responsible for scheduling, communication, and resource monitoring, can be invoked directly via the API or indirectly via CLI tools such as `kubectl`. It may also be accessed within client libraries such as Go or Python. By utilizing the API, administrators can interact with resources within the cluster such as listing or creating pods, which is a group of one or more containers. Adversaries call the API server via `curl` or other tools, allowing them to obtain further information about the environment such as pods, deployments, daemonsets, namespaces, or sysvars.(Citation: aquasec) They may also run various commands regarding resource management.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1059/013)

**Tactics**  [Execution](../../README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md)

## Procedure examples

- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has utilized the Docker command-line tool to gather details of the victim environment and collect credentials.(Citation: Hunt.io TeamPCP Toolkit MAY 2026) [Hunt.io TeamPCP Toolkit MAY 2026](https://hunt.io/blog/teampcp-python-toolkit-firescale-github-c2-takedown)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has leveraged Cisco Guest Shell to interact with a Linux Container on network devices.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)
- [G1056 - TeamPCP](../../../../Threat%20Intelligence/Groups/G1056%20-%20TeamPCP.md) — [TeamPCP](https://attack.mitre.org/groups/G1056) has queried the Kubernetes API for local service account tokens and has used `kubectl` for lateral movement.(Citation: Phoenix TeamPCP 20 MAY 2026)(Citation: Wiz TeamPCP KICS MAR 2026) [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action) · [Phoenix TeamPCP 20 MAY 2026](https://phoenix.security/teampcp-github-breach-durabletask-pypi-supply-chain-wave-four-2026/)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — TeamTNT targeted misconfigured containers and used container CLI tools.(Citation: Cisco Talos Blog) [Cisco Talos Blog](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Deny scripting where appropriate. Tools such as Python or Go can utilize Kubernetes and Docker within a client library and execute commands within their application.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict permissions on API access. RBAC in Kubernetes involve permissions that are additive, meaning there are no explicit "deny" rules. These permissions can be defined within a particular namespace or within cluster-scoped resources. Securing the Docker daemon can be done by using SSH or TLS with certificate authorization. Container management tools such as Docker and Podman may offer ways to run containers as rootless, which prevents them from running with privileged permissions.

## Detection strategies

- [DET0083 - Container CLI and API Abuse via Docker/Kubernetes (T1059.013)](../../../../Defenses/Detection%20Strategies/DET0083%20-%20Container%20CLI%20and%20API%20Abuse%20via%20Docker%20-%20Kubernetes%20%28T1059.013%29.md)

## Sources

- [Docker Desktop CLI](https://docs.docker.com/desktop/features/desktop-cli/)
- [Cisco Talos Blog](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/)
- [Intezer](https://intezer.com/blog/watch-your-containers-doki-infecting-docker-servers-in-the-cloud/)
- [aquasec](https://www.aquasec.com/blog/teamtnt-reemerged-with-new-aggressive-cloud-campaign/)
