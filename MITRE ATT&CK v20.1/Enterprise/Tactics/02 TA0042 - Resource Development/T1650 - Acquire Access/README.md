# T1650 - Acquire Access

[Enterprise](../../../README.md) / [Resource Development](../README.md)

Adversaries may purchase or otherwise acquire an existing access to a target system or network. A variety of online services and initial access broker networks are available to sell access to previously compromised systems.(Citation: Microsoft Ransomware as a Service)(Citation: CrowdStrike Access Brokers)(Citation: Krebs Access Brokers Fortune 500) In some cases, adversary groups may form partnerships to share compromised systems with each other.(Citation: CISA Karakurt 2022)

Footholds to compromised systems may take a variety of forms, such as access to planted backdoors (e.g., [Web Shell](https://attack.mitre.org/techniques/T1505/003)) or established access via [External Remote Services](https://attack.mitre.org/techniques/T1133). In some cases, access brokers will implant compromised systems with a “load” that can be used to install additional malware for paying customers.(Citation: Microsoft Ransomware as a Service)

By leveraging existing access broker networks rather than developing or obtaining their own initial access capabilities, an adversary can potentially reduce the resources required to gain a foothold on a target network and focus their efforts on later stages of compromise. Adversaries may prioritize acquiring access to systems that have been determined to lack security monitoring or that have high privileges, or systems that belong to organizations in a particular sector.(Citation: Microsoft Ransomware as a Service)(Citation: CrowdStrike Access Brokers)

In some cases, purchasing access to an organization in sectors such as IT contracting, software development, or telecommunications may allow an adversary to compromise additional victims via a [Trusted Relationship](https://attack.mitre.org/techniques/T1199), [Multi-Factor Authentication Interception](https://attack.mitre.org/techniques/T1111), or even [Supply Chain Compromise](https://attack.mitre.org/techniques/T1195).

**Note:** while this technique is distinct from other behaviors such as [Purchase Technical Data](https://attack.mitre.org/techniques/T1597/002) and [Credentials](https://attack.mitre.org/techniques/T1589/001), they may often be used in conjunction (especially where the acquired foothold requires [Valid Accounts](https://attack.mitre.org/techniques/T1078)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1650)

**Tactics**  [Resource Development](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Detection strategies

- [DET0884 - Detection of Acquire Access](../../../Defenses/Detection%20Strategies/DET0884%20-%20Detection%20of%20Acquire%20Access.md)

## Procedure examples

- [G1051 - Medusa Group](../../../Threat%20Intelligence/Groups/G1051%20-%20Medusa%20Group.md) — [Medusa Group](https://attack.mitre.org/groups/G1051) has purchased user credentials and other sensitive data from Initial Access Brokers (IABs).(Citation: Palo Alto Unit 42 Medusa Group Medusa Ransomware January 2024)(Citation: Check Point Medusa Ransomware April 2025)(Citation: CISA Medusa Group Medusa Ransomware March 2025)(Citation: Intel471 Medusa Ransomware May 2025) [Palo Alto Unit 42 Medusa Group Medusa Ransomware January 2024](https://unit42.paloaltonetworks.com/medusa-ransomware-escalation-new-leak-site/) · [Check Point Medusa Ransomware April 2025](https://www.checkpoint.com/cyber-hub/threat-prevention/ransomware/medusa-ransomware-group/) · [CISA Medusa Group Medusa Ransomware March 2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-071a) · [Intel471 Medusa Ransomware May 2025](https://www.intel471.com/blog/threat-hunting-case-study-medusa-ransomware)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [Krebs Access Brokers Fortune 500](https://krebsonsecurity.com/2012/10/service-sells-access-to-fortune-500-firms/)
- [CrowdStrike Access Brokers](https://www.crowdstrike.com/blog/access-brokers-targets-and-worth/)
- [CISA Karakurt 2022](https://www.cisa.gov/news-events/cybersecurity-advisories/aa22-152a)
- [Microsoft Ransomware as a Service](https://www.microsoft.com/en-us/security/blog/2022/05/09/ransomware-as-a-service-understanding-the-cybercrime-gig-economy-and-how-to-protect-yourself/)
