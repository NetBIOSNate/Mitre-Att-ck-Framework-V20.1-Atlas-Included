# AML.CS0023 - ShadowRay: Hijacking Exposed Ray Clusters

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Ray is an open-source Python framework for scaling production AI workflows. Ray's Job API allows for arbitrary remote execution by design. However, it does not offer authentication, and the default configuration may expose the cluster to the internet. Researchers at Oligo discovered that Ray clusters have been actively exploited for at least seven months. Adversaries can use victim organization's compute power and steal valuable information. The researchers estimate the value of the compromised machines to be nearly 1 billion USD.

Five vulnerabilities in Ray were reported to Anyscale, the maintainers of Ray. Anyscale promptly fixed four of the five vulnerabilities. However, the fifth vulnerability [CVE-2023-48022](https://nvd.nist.gov/vuln/detail/CVE-2023-48022) remains disputed. Anyscale maintains that Ray's lack of authentication is a design decision, and that Ray is meant to be deployed in a safe network environment. The Oligo researchers deem this a "shadow vulnerability" because in disputed status, the CVE does not show up in static scans.

**Type**  Incident

**Actor**  Unknown

**Target**  Exposed Ray Clusters

**Reporter**  Oligo Research Team

**Activity period**  2023-09-05

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0006 - Active Scanning](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md)

Adversaries can scan for public IP addresses to identify those potentially hosting Ray dashboards. Ray dashboards, by default, run on all network interfaces, which can expose them to the public internet if no other protective mechanisms are in place on the system.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

Once open Ray clusters have been identified, adversaries could use the Jobs API to invoke jobs onto accessible clusters. The Jobs API does not support any kind of authorization, so anyone with network access to the cluster can execute arbitrary code remotely.

**Next**  [S02](#step-s02), [S03](#step-s03), [S06](#step-s06)

### Step S02

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0035 - AI Artifact Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md)

Adversaries could collect AI artifacts including production models and data.

The researchers observed running production workloads from several organizations from a variety of industries.

**Next**  [S04](#step-s04)

### Step S03

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

The attackers could collect unsecured credentials stored in the cluster.

The researchers observed SSH keys, OpenAI tokens, HuggingFace tokens, Stripe tokens, cloud environment keys (AWS, GCP, Azure, Lambda Labs), Kubernetes secrets.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

AI artifacts, credentials, and other valuable information can be exfiltrated via cyber means.

The researchers found evidence of reverse shells on vulnerable clusters. They can be used to maintain persistence, continue to run arbitrary code, and exfiltrate.

**Next**  [S05](#step-s05), [S06](#step-s06)

### Step S05

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.003 - Model Repository](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.003%20-%20Model%20Repository/README.md)

HuggingFace tokens could allow the adversary to replace the victim organization's models with malicious variants.

**Next**  End of path

### Step S06

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.000 - Financial Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.000%20-%20Financial%20Harm/README.md)

Adversaries can cause financial harm to the victim organization. Exfiltrated credentials could be used to deplete credits or drain accounts. The GPU cloud resources themselves are costly. The researchers found evidence of cryptocurrency miners on vulnerable Ray clusters.

**Next**  End of path

## References

- [Anyscale Update on CVEs](https://www.anyscale.com/blog/update-on-ray-cves-cve-2023-6019-cve-2023-6020-cve-2023-6021-cve-2023-48022-cve-2023-48023)
- [CVE-2023-48022](https://nvd.nist.gov/vuln/detail/CVE-2023-48022)
- [ShadowRay: First Known Attack Campaign Targeting AI Workloads Actively Exploited In The Wild](https://www.oligo.security/blog/shadowray-attack-ai-workloads-actively-exploited-in-the-wild)
- [ShadowRay: AI Infrastructure Is Being Exploited In the Wild](https://protectai.com/threat-research/shadowray-ai-infrastructure-is-being-exploited-in-the-wild)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0023)
