# T0828 - Loss of Productivity and Revenue

[ICS](../../../README.md) / [Impact](../README.md)

Adversaries may cause loss of productivity and revenue through disruption and even damage to the availability and integrity of control system operations, devices, and related processes. This technique may manifest as a direct effect of an ICS-targeting attack or tangentially, due to an IT-targeting attack against non-segregated environments. 

In cases where these operations or services are brought to a halt, the loss of productivity may eventually present an impact for the end-users or consumers of products and services. The disrupted supply-chain may result in supply shortages and increased prices, among other consequences. 

A ransomware attack on an Australian beverage company resulted in the shutdown of some manufacturing sites, including precautionary halts to protect key systems. (Citation: Paganini, Pierluigi June 2020) The company announced the potential for temporary shortages of their products following the attack. (Citation: Paganini, Pierluigi June 2020) (Citation: Lion Corporation June 2020) 

In the 2021 Colonial Pipeline ransomware incident, the pipeline was unable to transport approximately 2.5 million barrels of fuel per day to the East Coast.  (Citation: Colonial Pipeline Company May 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0828)

**Tactics**  [Impact](../README.md)

**Platforms**  [No platform specified](../../../Platforms/None.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), power breakers were opened which caused the operating companies to be unable to deliver power, and left thousands of businesses and households without power for around 6 hours. (Citation: Ukraine15 - EISAC - 201603)(Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf) · [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [S0606 - Bad Rabbit](../../../Threat%20Intelligence/Software/Malware/S0606%20-%20Bad%20Rabbit.md) — Several transportation organizations in Ukraine have suffered from being infected by [Bad Rabbit](https://attack.mitre.org/software/S0606), resulting in some computers becoming encrypted, according to media reports. (Citation: ESET Bad Rabbit) [ESET Bad Rabbit](https://www.welivesecurity.com/2017/10/24/bad-rabbit-not-petya-back/)
- [S0608 - Conficker](../../../Threat%20Intelligence/Software/Malware/S0608%20-%20Conficker.md) — A [Conficker](https://attack.mitre.org/software/S0608) infection at a nuclear power plant forced the facility to shutdown and go through security procedures involved with such events, with its staff scanning computer systems and going through all the regular checks and motions before putting the plant back into production. (Citation: Catalin Cimpanu April 2016) [Catalin Cimpanu April 2016](https://news.softpedia.com/news/on-chernobyl-s-30th-anniversary-malware-shuts-down-german-nuclear-power-plant-503429.shtml)
- [S0605 - EKANS](../../../Threat%20Intelligence/Software/Malware/S0605%20-%20EKANS.md) — [EKANS](https://attack.mitre.org/software/S0605) infection resulted in a temporary production loss within a Honda manufacturing plant. (Citation: Davey Winder June 2020) [Davey Winder June 2020](https://www.forbes.com/sites/daveywinder/2020/06/10/honda-hacked-japanese-car-giant-confirms-cyber-attack-on-global-operations-snake-ransomware/?sh=2725c35753ad)
- [S0372 - LockerGoga](../../../Threat%20Intelligence/Software/Malware/S0372%20-%20LockerGoga.md) — While Norsk Hydro attempted to recover from a [LockerGoga](https://attack.mitre.org/software/S0372) infection, most of its 160 manufacturing locations switched to manual (non-IT driven) operations. Manual operations can result in a loss of productivity. (Citation: Kevin Beaumont)(Citation: Hydro) [Hydro](https://www.hydro.com/en/media/on-the-agenda/cyber-attack/) · [Kevin Beaumont](https://doublepulsar.com/how-lockergoga-took-down-hydro-ransomware-used-in-targeted-attacks-aimed-at-big-business-c666551f5880)
- [S0368 - NotPetya](../../../Threat%20Intelligence/Software/Malware/S0368%20-%20NotPetya.md) — [NotPetya](https://attack.mitre.org/software/S0368) disrupted manufacturing facilities supplying vaccines, resulting in a halt of production and the inability to meet demand for specific vaccines. (Citation: David Voreacos, Katherine Chinglinsky, Riley Griffin December 2019) [David Voreacos, Katherine Chinglinsky, Riley Griffin December 2019](https://www.bloomberg.com/news/features/2019-12-03/merck-cyberattack-s-1-3-billion-question-was-it-an-act-of-war)
- [S0496 - REvil](../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — The [REvil](https://attack.mitre.org/software/S0496) malware gained access to an organizations network and encrypted sensitive files used by OT equipment. (Citation: Selena Larson, Camille Singleton December 2020) [Selena Larson, Camille Singleton December 2020](https://f.hubspotusercontent10.net/hubfs/5943619/Whitepaper-Downloads/Ransomware_in_ICS_Environments_Whitepaper_10_12_20.pdf)
- [S0446 - Ryuk](../../../Threat%20Intelligence/Software/Malware/S0446%20-%20Ryuk.md) — An enterprise resource planning (ERP) manufacturing server was lost to the [Ryuk](https://attack.mitre.org/software/S0446) attack. The manufacturing process had to rely on paper and existing orders to keep the shop floor open. (Citation: Kelly Jackson Higgins) [Kelly Jackson Higgins](https://www.darkreading.com/attacks-breaches/how-a-manufacturing-firm-recovered-from-a-devastating-ransomware-attack/d/d-id/1334760)
- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) tripped a controller into a failed safe state, which caused an automatic shutdown of the plant, this resulted in a pause of plant operations for more than a week. Thereby impacting industrial processes and halting productivity.(Citation: FireEye TRITON Dec 2017) [FireEye TRITON Dec 2017](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html)
- [C0031 - Unitronics Defacement Campaign](../../../Threat%20Intelligence/Campaigns/C0031%20-%20Unitronics%20Defacement%20Campaign.md) — During the [Unitronics Defacement Campaign](https://attack.mitre.org/campaigns/C0031), the [CyberAv3ngers](https://attack.mitre.org/groups/G1027) caused multiple businesses to halt operations in their industrial environments, impacting their typical business operations. These victims covered multiple sectors.(Citation: Jamie Tarabay and Katrina Manson December 2023) [Jamie Tarabay and Katrina Manson December 2023](https://www.bloomberg.com/news/articles/2023-12-22/iranian-linked-hacks-expose-failure-to-safeguard-us-water-system)

## Detection strategies

- [DET0757 - Detection of Loss of Productivity and Revenue](../../../Defenses/Detection%20Strategies/DET0757%20-%20Detection%20of%20Loss%20of%20Productivity%20and%20Revenue.md)

## Mitigations

- [M0953 - Data Backup](../../../Defenses/Mitigations/M0953%20-%20Data%20Backup.md) — Take and store data backups from end user systems and critical servers. Ensure backup and storage systems are hardened and kept separate from the corporate network to prevent compromise. Maintain and exercise incident response plans (Citation: Department of Homeland Security October 2009), including the management of gold-copy back-up images and configurations for key systems to enable quick recovery and response from adversarial activities that impact control, view, or availability. [Department of Homeland Security October 2009](https://us-cert.cisa.gov/sites/default/files/recommended_practices/final-RP_ics_cybersecurity_incident_response_100609.pdf)

## Sources

- [Colonial Pipeline Company May 2021](https://www.colpipe.com/news/press-releases/media-statement-colonial-pipeline-system-disruption)
- [Lion Corporation June 2020](https://lionco.com/2020/06/26/lion-update-re-cyber-issue/)
- [Paganini, Pierluigi June 2020](https://securityaffairs.co/wordpress/104749/cyber-crime/ransomware-attack-hit-lion.html)
