# T1583.005 - Botnet

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1583 - Acquire Infrastructure](../README.md)

Adversaries may buy, lease, or rent a network of compromised systems that can be used during targeting. A botnet is a network of compromised systems that can be instructed to perform coordinated tasks.(Citation: Norton Botnet) Adversaries may purchase a subscription to use an existing botnet from a booter/stresser service. 

Internet-facing edge devices and related network appliances that are end-of-life (EOL) and unsupported by their manufacturers are commonly acquired for botnet activities. Adversaries may lease operational relay box (ORB) networks – consisting of virtual private servers (VPS), small office/home office (SOHO) routers, or Internet of Things (IoT) devices – to serve as a botnet.(Citation: ORB Mandiant) 

With a botnet at their disposal, adversaries may perform follow-on activity such as large-scale [Phishing](https://attack.mitre.org/techniques/T1566) or Distributed Denial of Service (DDoS).(Citation: Imperva DDoS for Hire)(Citation: Krebs-Anna)(Citation: Krebs-Bazaar)(Citation: Krebs-Booter) Acquired botnets may also be used to support Command and Control activity, such as [Hide Infrastructure](https://attack.mitre.org/techniques/T1665) through an established [Proxy](https://attack.mitre.org/techniques/T1090) network.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1583/005)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G1023 - APT5](../../../../Threat%20Intelligence/Groups/G1023%20-%20APT5.md) — [APT5](https://attack.mitre.org/groups/G1023) has acquired a network of compromised systems – specifically an ORB (operational relay box) network – for follow on activities.(Citation: ORB Mandiant) [ORB Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-orb-networks)
- [G0125 - HAFNIUM](../../../../Threat%20Intelligence/Groups/G0125%20-%20HAFNIUM.md) — [HAFNIUM](https://attack.mitre.org/groups/G0125) has incorporated leased devices into covert networks to obfuscate communications.(Citation: Microsoft Silk Typhoon MAR 2025) [Microsoft Silk Typhoon MAR 2025](https://www.microsoft.com/en-us/security/blog/2025/03/05/silk-typhoon-targeting-it-supply-chain/)
- [G0004 - Ke3chang](../../../../Threat%20Intelligence/Groups/G0004%20-%20Ke3chang.md) — [Ke3chang](https://attack.mitre.org/groups/G0004) has utilized an ORB (operational relay box) network for reconnaissance and vulnerability exploitation.(Citation: ORB Mandiant) [ORB Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-orb-networks)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0837 - Detection of Botnet](../../../../Defenses/Detection%20Strategies/DET0837%20-%20Detection%20of%20Botnet.md)

## Sources

- [Krebs-Booter](https://krebsonsecurity.com/2016/10/are-the-days-of-booter-services-numbered/)
- [Krebs-Bazaar](https://krebsonsecurity.com/2016/10/hackforums-shutters-booter-service-bazaar/)
- [Krebs-Anna](https://krebsonsecurity.com/2017/01/who-is-anna-senpai-the-mirai-worm-author/)
- [Imperva DDoS for Hire](https://www.imperva.com/learn/ddos/booters-stressers-ddosers/)
- [Norton Botnet](https://us.norton.com/internetsecurity-malware-what-is-a-botnet.html)
- [ORB Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-orb-networks)
