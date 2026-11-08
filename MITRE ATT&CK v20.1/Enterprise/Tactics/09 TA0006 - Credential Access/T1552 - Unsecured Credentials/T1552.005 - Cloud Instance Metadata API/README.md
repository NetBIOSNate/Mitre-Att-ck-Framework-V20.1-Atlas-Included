# T1552.005 - Cloud Instance Metadata API

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1552 - Unsecured Credentials](../README.md)

Adversaries may attempt to access the Cloud Instance Metadata API to collect credentials and other sensitive data.

Most cloud service providers support a Cloud Instance Metadata API which is a service provided to running virtual instances that allows applications to access information about the running virtual instance. Available information generally includes name, security group, and additional metadata including sensitive data such as credentials and UserData scripts that may contain additional secrets. The Instance Metadata API is provided as a convenience to assist in managing applications and is accessible by anyone who can access the instance.(Citation: AWS Instance Metadata API) A cloud metadata API has been used in at least one high profile compromise.(Citation: Krebs Capital One August 2019)

If adversaries have a presence on the running virtual instance, they may query the Instance Metadata API directly to identify credentials that grant access to additional resources. Additionally, adversaries may exploit a Server-Side Request Forgery (SSRF) vulnerability in a public facing web proxy that allows them to gain access to the sensitive information via a request to the Instance Metadata API.(Citation: RedLock Instance Metadata API 2018)

The de facto standard across cloud service providers is to host the Instance Metadata API at <code>http[:]//169.254.169.254</code>.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1552/005)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md)

## Detection strategies

- [DET0001 - Detect Access to Cloud Instance Metadata API (IaaS)](../../../../Defenses/Detection%20Strategies/DET0001%20-%20Detect%20Access%20to%20Cloud%20Instance%20Metadata%20API%20%28IaaS%29.md)

## Procedure examples

- [S9045 - BACKUPOSINT v9.0 APEX PREDATOR](../../../../Threat%20Intelligence/Software/Malware/S9045%20-%20BACKUPOSINT%20v9.0%20APEX%20PREDATOR.md) — [BACKUPOSINT v9.0 APEX PREDATOR](https://attack.mitre.org/software/S9045) has a module that is capable of gathering Cloud Instance Metadata to include AWS, Google Cloud Platform, and Azure.(Citation: AI-Mexico-Govt-Compromise) [AI-Mexico-Govt-Compromise](https://5943619.hs-sites.com/hubfs/116-Whitepapers/dragos-2026-ai-mexico-water-attack-intel-brief.pdf)
- [S0601 - Hildegard](../../../../Threat%20Intelligence/Software/Malware/S0601%20-%20Hildegard.md) — [Hildegard](https://attack.mitre.org/software/S0601) has queried the Cloud Instance Metadata API for cloud credentials.(Citation: Unit 42 Hildegard Malware) [Unit 42 Hildegard Malware](https://unit42.paloaltonetworks.com/hildegard-malware-teamtnt/)
- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has gathered credentials and secrets from AWS, Google Cloud Platform (GCP) and Azure metadata API.(Citation: Hunt.io TeamPCP Toolkit MAY 2026)(Citation: Flashpoint Mini Shai-Hulud MAY 2026) [Flashpoint Mini Shai-Hulud MAY 2026](https://flashpoint.io/blog/mini-shai-hulud-worm-new-era-ci-cd-exploitation/) · [Hunt.io TeamPCP Toolkit MAY 2026](https://hunt.io/blog/teampcp-python-toolkit-firescale-github-c2-takedown)
- [S0683 - Peirates](../../../../Threat%20Intelligence/Software/Tools/S0683%20-%20Peirates.md) — [Peirates](https://attack.mitre.org/software/S0683) can query the query AWS and GCP metadata APIs for secrets.(Citation: Peirates GitHub) [Peirates GitHub](https://github.com/inguardians/peirates)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has queried the AWS and GCP metadata endpoints for instances and service credentials.(Citation: Aikido Shai-Hulud September 2025) [Aikido Shai-Hulud September 2025](https://www.aikido.dev/blog/s1ngularity-nx-attackers-strike-again)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has queried the AWS instance metadata service for credentials.(Citation: Trend Micro TeamTNT)(Citation: Cisco Talos Intelligence Group) [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/) · [Trend Micro TeamTNT](https://documents.trendmicro.com/assets/white_papers/wp-tracking-the-activities-of-teamTNT.pdf)
- [S9009 - TruffleHog](../../../../Threat%20Intelligence/Software/Tools/S9009%20-%20TruffleHog.md) — [TruffleHog](https://attack.mitre.org/software/S9009) can query the AWS and GCP metadata endpoints for instances and service credentials.(Citation: Black Hills Information Security TruffleHog January 2024)(Citation: Github TruffleSecurity Trufflehog April 2025) [Black Hills Information Security TruffleHog January 2024](https://www.blackhillsinfosec.com/rooting-for-secrets-with-trufflehog/) · [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable unnecessary metadata services and restrict or disable insecure versions of metadata services that are in use to prevent adversary access.(Citation: Amazon AWS IMDS V2) [Amazon AWS IMDS V2](https://aws.amazon.com/blogs/security/defense-in-depth-open-firewalls-reverse-proxies-ssrf-vulnerabilities-ec2-instance-metadata-service/)
- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Limit access to the Instance Metadata API. A properly configured Web Application Firewall (WAF) may help prevent external adversaries from exploiting Server-side Request Forgery (SSRF) attacks that allow access to the Cloud Instance Metadata API.(Citation: RedLock Instance Metadata API 2018) [RedLock Instance Metadata API 2018](https://redlock.io/blog/instance-metadata-api-a-modern-day-trojan-horse)
- [M1035 - Limit Access to Resource Over Network](../../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Limit access to the Instance Metadata API using a host-based firewall such as iptables.

## Sources

- [AWS Instance Metadata API](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html)
- [RedLock Instance Metadata API 2018](https://redlock.io/blog/instance-metadata-api-a-modern-day-trojan-horse)
- [Krebs Capital One August 2019](https://krebsonsecurity.com/2019/08/what-we-can-learn-from-the-capital-one-hack/)
