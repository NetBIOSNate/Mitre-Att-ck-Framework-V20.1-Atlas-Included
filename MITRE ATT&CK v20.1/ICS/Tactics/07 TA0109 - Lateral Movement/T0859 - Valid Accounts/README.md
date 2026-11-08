# T0859 - Valid Accounts

[ICS](../../../README.md) / [Lateral Movement](../README.md)

Adversaries may steal the credentials of a specific user or service account using credential access techniques. In some cases, default credentials for control system devices may be publicly available. Compromised credentials may be used to bypass access controls placed on various resources on hosts and within the network, and may even be used for persistent access to remote systems. Compromised and default credentials may also grant an adversary increased privilege to specific systems and devices or access to restricted areas of the network. Adversaries may choose not to use malware or tools, in conjunction with the legitimate access those credentials provide, to make it harder to detect their presence or to control devices and send legitimate commands in an unintended way. 

Adversaries may also create accounts, sometimes using predefined account names and passwords, to provide a means of backup access for persistence. (Citation: Booz Allen Hamilton) 

The overlap of credentials and permissions across a network of systems is of concern because the adversary may be able to pivot across accounts and systems to reach a high level of access (i.e., domain or enterprise administrator)  and possibly between the enterprise and operational technology environments. Adversaries may be able to leverage valid credentials from one system to gain access to another system.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0859)

**Tactics**  [Persistence](../../03%20TA0110%20-%20Persistence/README.md), [Lateral Movement](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) used valid accounts to laterally move through VPN connections and dual-homed systems. Sandworm Team used the credentials of valid accounts to interact with client applications and access employee workstations hosting HMI applications. (Citation: Ukraine15 - EISAC - 201603)(Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf) · [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [C0025 - 2016 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) used valid accounts to laterally move through VPN connections and dual-homed systems.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used valid accounts to access Hitatchi RTUs, Mikronika RTUs, Hitachi Relion Protection and Control Relays, Mikronika HMI Computers, and Moxa NPort Serial Device Servers.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [G1000 - ALLANITE](../../../Threat%20Intelligence/Groups/G1000%20-%20ALLANITE.md) — [ALLANITE](https://attack.mitre.org/groups/G1000) utilized credentials collected through phishing and watering hole attacks. (Citation: Dragos) [Dragos](https://dragos.com/resource/allanite/)
- [S0089 - BlackEnergy](../../../Threat%20Intelligence/Software/Malware/S0089%20-%20BlackEnergy.md) — [BlackEnergy](https://attack.mitre.org/software/S0089) utilizes valid user and administrator credentials, in addition to creating new administrator accounts to maintain presence. (Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can brute force password-based authentication to Schneider PLCs over the CODESYS protocol (UDP port 1740).(Citation: CISA-AA22-103A) [INCONTROLLER](https://attack.mitre.org/software/S1045) can perform brute force guessing of passwords to OPC UA servers using a predefined list of passwords.(Citation: CISA-AA22-103A)(Citation: Wylie-22) [CISA-AA22-103A](https://www.cisa.gov/uscert/ncas/alerts/aa22-103a) · [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [G0049 - OilRig](../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) utilized stolen credentials to gain access to victim machines.(Citation: Dragos) [Dragos](https://dragos.com/resource/chrysene/)
- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) used valid credentials when laterally moving through RDP jump boxes into the ICS environment.(Citation: FireEye TRITON 2018) [FireEye TRITON 2018](https://web.archive.org/web/20200618231942/https://www.fireeye.com/blog/threat-research/2018/06/totally-tubular-treatise-on-triton-and-tristation.html)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Authenticate all access to field controllers before authorizing access to, or modification of, a device's state, logic, or programs. Centralized authentication techniques can help manage the large number of field controller accounts needed across the ICS.
- [M0936 - Account Use Policies](../../../Defenses/Mitigations/M0936%20-%20Account%20Use%20Policies.md) — Configure features related to account use like login attempt lockouts, specific login times, and password strength requirements as examples. Consider these features as they relate to assets which may impact safety and availability. (Citation: Keith Stouffer May 2015) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf)
- [M0915 - Active Directory Configuration](../../../Defenses/Mitigations/M0915%20-%20Active%20Directory%20Configuration.md) — Consider configuration and use of a network-wide authentication service such as Active Directory, LDAP, or RADIUS capabilities which can be found in ICS devices. (Citation: Keith Stouffer May 2015) (Citation: Schweitzer Engineering Laboratories August 2015) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [Schweitzer Engineering Laboratories August 2015](https://cdn.selinc.com/assets/Literature/Publications/Application%20Notes/AN2015-08_20150817.pdf?)
- [M0913 - Application Developer Guidance](../../../Defenses/Mitigations/M0913%20-%20Application%20Developer%20Guidance.md) — Ensure that applications and devices do not store sensitive data or credentials insecurely (e.g., plaintext credentials in code, published credentials in repositories, or credentials in public cloud storage). (Citation: CISA June 2013) [CISA June 2013](https://us-cert.cisa.gov/ncas/alerts/TA13-175A)
- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Routinely audit source code, application configuration files, open repositories, and public cloud storage for insecure use and storage of credentials.
- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Consider using IP allowlisting along with user account management to ensure that data access is restricted not only to valid users but only from expected IP ranges to mitigate the use of stolen credentials to access data.
- [M0932 - Multi-factor Authentication](../../../Defenses/Mitigations/M0932%20-%20Multi-factor%20Authentication.md) — Integrating multi-factor authentication (MFA) as part of organizational policy can greatly reduce the risk of an adversary gaining access to valid credentials that may be used for additional tactics such as initial access, lateral movement, and collecting information. MFA can also be used to restrict access to cloud resources and APIs.
- [M0927 - Password Policies](../../../Defenses/Mitigations/M0927%20-%20Password%20Policies.md) — Applications and appliances that utilize default username and password should be changed immediately after the installation, and before deployment to a production environment. (Citation: CISA June 2013) [CISA June 2013](https://us-cert.cisa.gov/ncas/alerts/TA13-175A)
- [M0926 - Privileged Account Management](../../../Defenses/Mitigations/M0926%20-%20Privileged%20Account%20Management.md) — Audit domain and local accounts and their permission levels routinely to look for situations that could allow an adversary to gain system wide access with stolen privileged account credentials. (Citation: Microsoft May 2017) (Citation: Microsoft August 2018)These audits should also identify if default accounts have been enabled, or if new local accounts are created that have not be authorized. Follow best practices for design and administration of an enterprise network to limit privileged account use across administrative tiers. (Citation: Microsoft February 2019) [Microsoft May 2017](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/attractive-accounts-for-credential-theft) · [Microsoft August 2018](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/implementing-least-privilege-administrative-models) · [Microsoft February 2019](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material#a-nameesaebmaesae-administrative-forest-design-approach)
- [M0918 - User Account Management](../../../Defenses/Mitigations/M0918%20-%20User%20Account%20Management.md) — Ensure users and user groups have appropriate permissions for their roles through Identity and Access Management (IAM) controls. Implement strict IAM controls to prevent access to systems except for the applications, users, and services that require access. Implement user accounts for each individual for enforcement and non-repudiation of actions.

## Detection strategies

- [DET0724 - Detection of Valid Accounts](../../../Defenses/Detection%20Strategies/DET0724%20-%20Detection%20of%20Valid%20Accounts.md)

## Sources

- [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf)
