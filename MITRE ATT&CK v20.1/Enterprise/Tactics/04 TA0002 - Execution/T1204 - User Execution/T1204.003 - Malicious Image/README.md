# T1204.003 - Malicious Image

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1204 - User Execution](../README.md)

Adversaries may rely on a user running a malicious image to facilitate execution. Amazon Web Services (AWS) Amazon Machine Images (AMIs), Google Cloud Platform (GCP) Images, and Azure Images as well as popular container runtimes such as Docker can be backdoored. Backdoored images may be uploaded to a public repository via [Upload Malware](https://attack.mitre.org/techniques/T1608/001), and users may then download and deploy an instance or container from the image without realizing the image is malicious, thus bypassing techniques that specifically achieve Initial Access. This can lead to the execution of malicious code, such as code that executes cryptocurrency mining, in the instance or container.(Citation: Summit Route Malicious AMIs)

Adversaries may also name images a certain way to increase the chance of users mistakenly deploying an instance or container from the image (ex: [Match Legitimate Resource Name or Location](https://attack.mitre.org/techniques/T1036/005)).(Citation: Aqua Security Cloud Native Threat Report June 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1204/003)

**Tactics**  [Execution](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [Containers](../../../../Platforms/Containers.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Audit images deployed within the environment to ensure they do not contain any malicious components.
- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Utilize a trust model such as Docker Content Trust with digital signatures to ensure runtime verification of the integrity and publisher of specific image tags.(Citation: Content trust in Docker)(Citation: Content trust in Azure Container Registry) [Content trust in Docker](https://docs.docker.com/engine/security/trust/content_trust/) · [Content trust in Azure Container Registry](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-content-trust)
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network prevention intrusion systems and systems designed to scan and remove malicious downloads can be used to block activity.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to be aware of the existence of malicious images and how to avoid deploying instances and containers from them.

## Detection strategies

- [DET0248 - User Execution – Malicious Image (containers & IaaS) – pull/run → start → anomalous behavior (T1204.003)](../../../../Defenses/Detection%20Strategies/DET0248%20-%20User%20Execution%20%E2%80%93%20Malicious%20Image%20%28containers%20%26%20IaaS%29%20%E2%80%93%20pull%20-%20run%20%E2%86%92%20start%20%E2%86%92%20anomalous.md)

## Procedure examples

- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has relied on users to download and execute malicious Docker images.(Citation: Lacework TeamTNT May 2021) [Lacework TeamTNT May 2021](https://www.lacework.com/blog/taking-teamtnt-docker-images-offline)

## Sources

- [Summit Route Malicious AMIs](https://summitroute.com/blog/2018/09/24/investigating_malicious_amis/)
- [Aqua Security Cloud Native Threat Report June 2021](https://web.archive.org/web/20220106180157/https://info.aquasec.com/hubfs/Threat%20reports/AquaSecurity_Cloud_Native_Threat_Report_2021.pdf)
