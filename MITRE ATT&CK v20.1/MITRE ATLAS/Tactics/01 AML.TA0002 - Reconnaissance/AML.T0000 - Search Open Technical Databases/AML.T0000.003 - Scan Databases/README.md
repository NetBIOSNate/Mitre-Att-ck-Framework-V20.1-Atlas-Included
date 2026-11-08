# AML.T0000.003 - Scan Databases

[MITRE ATLAS](../../../../README.md) / [AML.TA0002 - Reconnaissance](../../README.md) / [AML.T0000 - Search Open Technical Databases](../README.md)

Adversaries may search public internet-scan services to identify a victim's exposed AI infrastructure. These services, such as Shodan and Censys, continuously scan the internet and publish the active IP addresses, hostnames, open ports, and service banners, which adversaries can query without interacting with the target directly. 

Information gathered this way may also reveal candidates for follow-on [Active Scanning](../../AML.T0006%20-%20Active%20Scanning/README.md) to confirm that services remain reachable, to probe for misconfigurations or unauthorized endpoints. It may also inform later initial access attempts such as [Exploit Public-Facing Application](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md). Unlike [Active Scanning](../../AML.T0006%20-%20Active%20Scanning/README.md), this technique relies on third-party scan data and involves no direct interaction with the victim system.

**Tactics**  [AML.TA0002 - Reconnaissance](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1596.005](../../../../../Enterprise/Tactics/01%20TA0043%20-%20Reconnaissance/T1596%20-%20Search%20Open%20Technical%20Databases/T1596.005%20-%20Scan%20Databases/README.md) · [MITRE ATT&CK T1596.005](https://attack.mitre.org/techniques/T1596/005/)

## Case studies

- [AML.CS0048 - Exposed ClawdBot Control Interfaces Leads to Credential Access and Execution](../../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md) · [S00](../../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md#step-s00)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S08](../../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s08)

## Mitigations

- [AML.M0039 - AI Honeypots](../../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Decoy assets are catalogued by the same internet scan databases (e.g., Shodan, Censys) that adversaries query to locate exposed AI infrastructure. Adversarial engagement that originates from those platforms can grant defenders visibility into those discovery channels.

## Software implementations

- [AML.S0030 - Shodan](../../../../Software/Tools/AML.S0030%20-%20Shodan.md) — [Shodan](../../../../Software/Tools/AML.S0030%20-%20Shodan.md) provides searchable internet-scan results containing service banners, HTTP titles, software identifiers, IP addresses, and open ports. Its web interface and API allow users to locate exposed AI services and supporting infrastructure by querying indexed fingerprints without directly probing each target.[[source-1]]
- [AML.S0031 - FOFA](../../../../Software/Tools/AML.S0031%20-%20FOFA.md) — [FOFA](../../../../Software/Tools/AML.S0031%20-%20FOFA.md) makes internet-scan results searchable through a web interface and API. Users can query indexed service fingerprints and HTTP content to identify exposed AI applications and supporting infrastructure, retrieve candidate hosts, and compare deployment counts without directly probing each target. [product-overview](https://en.fofa.info/about/en) [source-1](https://en.fofa.info/api)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0000.003)
