# DC0072 - Container Creation

[Enterprise](../../README.md) / [Data Components](README.md)

"Container Creation" data component captures details about the initial construction of a container in a containerized environment. This includes events where a new container is instantiated, such as through Docker, Kubernetes, or other container orchestration platforms. Monitoring these events helps detect unauthorized or potentially malicious container creation. Examples:

- Docker Example: `docker create my-container`, `docker run --name=my-container nginx:latest`
- Kubernetes Example: `kubectl run my-pod --image=nginx`, `kubectl create deployment my-deployment --image=nginx`
- Cloud Container Services Example
    - AWS ECS: Task or service creation (`RunTask` or `CreateService`).
    - Azure Container Instances: Deployment of a container group.
    - Google Kubernetes Engine (GKE): Creation of new pods via GCP APIs.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0072)

## Log sources and channels

- **kubernetes:apiserver** — create/exec: Kubernetes API calls to exec into containers or create pods from curl, kubectl, or SDK clients
- **kubernetes:events** — container start/stop activity via Docker, containerd, or CRI-O
- **docker:daemon** — container create/start with privileged flag or host volume mount
- **kubernetes:audit** — create: Pod/Container created with image tag 'latest' or mutable tag; imagePullPolicy=Always; noDigest=true
- **systemd:unit** — container run with restart policy set to 'always' or 'unless-stopped'
- **docker:events** — created,started: new container from untrusted registry or unexpected entrypoint
- **containerd:events** — create
- **docker:events** — docker run with restart=always or modifying init

## Analytics using this component

- [AN0233 - Analytic 0233](../Analytics/AN0233.md)
- [AN0582 - Analytic 0582](../Analytics/AN0582.md)
- [AN0612 - Analytic 0612](../Analytics/AN0612.md)
- [AN0691 - Analytic 0691](../Analytics/AN0691.md)
- [AN1304 - Analytic 1304](../Analytics/AN1304.md)
- [AN1317 - Analytic 1317](../Analytics/AN1317.md)
- [AN1492 - Analytic 1492](../Analytics/AN1492.md)
- [AN1578 - Analytic 1578](../Analytics/AN1578.md)
