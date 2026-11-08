# T0826 - Loss of Availability

[ICS](../../../README.md) / [Impact](../README.md)

Adversaries may attempt to disrupt essential components or systems to prevent owner and operator from delivering products or services. (Citation: Corero) (Citation: Michael J. Assante and Robert M. Lee) (Citation: Tyson Macaulay) 

Adversaries may leverage malware to delete or encrypt critical data on HMIs, workstations, or databases.

In the 2021 Colonial Pipeline ransomware incident, pipeline operations were temporally halted on May 7th and were not fully restarted until May 12th. (Citation: Colonial Pipeline Company May 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0826)

**Tactics**  [Impact](../README.md)

**Platforms**  [No platform specified](../../../Platforms/None.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) opened the breakers at the infected sites, shutting the power off for thousands of businesses and households for around 6 hours. (Citation: Ukraine15 - EISAC - 201603)(Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf) · [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [C0066 - 2026 U.S. Water Utilities Attacks](../../../Threat%20Intelligence/Campaigns/C0066%20-%202026%20U.S.%20Water%20Utilities%20Attacks.md) — During the [2026 U.S. Water Utilities Attacks](https://attack.mitre.org/campaigns/C0066), the adversary temporarily shut down the well and water treatment plant, causing loss of cellular connectivity across multiple sites interrupting the service the plant provides leading operators to revert to manual operations.(Citation: Tenable Minnesota Water Utilities)(Citation: Dragos Water Under Attack) During the [2026 U.S. Water Utilities Attacks](https://attack.mitre.org/campaigns/C0066), the adversary caused loss of water pressure and flooding at affected water and wastewater utilities.(Citation: FBI Water and Wastewater) [FBI Water and Wastewater](https://www.fbi.gov/investigate/cyber/alerts/2026/malicious-cyber-actors-targeting-water-and-wastewater-sector-internet--facing-programmable-logic-controllers-causing-operational-disruptions) · [Dragos Water Under Attack](https://www.dragos.com/blog/water-utility-attacks-decade-of-gaps) · [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know)
- [S0608 - Conficker](../../../Threat%20Intelligence/Software/Malware/S0608%20-%20Conficker.md) — A [Conficker](https://attack.mitre.org/software/S0608) infection at a nuclear power plant forced the facility to temporarily shutdown. (Citation: Catalin Cimpanu April 2016) [Catalin Cimpanu April 2016](https://news.softpedia.com/news/on-chernobyl-s-30th-anniversary-malware-shuts-down-german-nuclear-power-plant-503429.shtml)
- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) degraded operations across at least seven states that resulted in reported incidents, pressure loss and flooding.(Citation: Tenable Minnesota Water Utilities) [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know)
- [C0041 - FrostyGoop Incident](../../../Threat%20Intelligence/Campaigns/C0041%20-%20FrostyGoop%20Incident.md) — During [FrostyGoop Incident](https://attack.mitre.org/campaigns/C0041), the adversary modified victim control system parameters resulting in the loss of heating services to impacted district heating customers.(Citation: Dragos FROSTYGOOP 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [C0031 - Unitronics Defacement Campaign](../../../Threat%20Intelligence/Campaigns/C0031%20-%20Unitronics%20Defacement%20Campaign.md) — During the [Unitronics Defacement Campaign](https://attack.mitre.org/campaigns/C0031), the [CyberAv3ngers](https://attack.mitre.org/groups/G1027) caused multiple businesses to halt operations due to the unavailability of the [Programmable Logic Controller (PLC)](https://attack.mitre.org/assets/A0003) and [Human-Machine Interface (HMI)](https://attack.mitre.org/assets/A0002). These victims covered multiple sectors.(Citation: Jamie Tarabay and Katrina Manson December 2023) [Jamie Tarabay and Katrina Manson December 2023](https://www.bloomberg.com/news/articles/2023-12-22/iranian-linked-hacks-expose-failure-to-safeguard-us-water-system)

## Mitigations

- [M0953 - Data Backup](../../../Defenses/Mitigations/M0953%20-%20Data%20Backup.md) — Take and store data backups from end user systems and critical servers. Ensure backup and storage systems are hardened and kept separate from the corporate network to prevent compromise. Maintain and exercise incident response plans (Citation: Department of Homeland Security October 2009), including the management of gold-copy back-up images and configurations for key systems to enable quick recovery and response from adversarial activities that impact control, view, or availability. [Department of Homeland Security October 2009](https://us-cert.cisa.gov/sites/default/files/recommended_practices/final-RP_ics_cybersecurity_incident_response_100609.pdf)
- [M0810 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Provide operators with redundant, out-of-band communication to support monitoring and control of the operational processes, especially when recovering from a network outage (Citation: National Institute of Standards and Technology April 2013). Out-of-band communication should utilize diverse systems and technologies to minimize common failure modes and vulnerabilities within the communications infrastructure. For example, wireless networks (e.g., 3G, 4G) can be used to provide diverse and redundant delivery of data. [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0811 - Redundancy of Service](../../../Defenses/Mitigations/M0811%20-%20Redundancy%20of%20Service.md) — Hot-standbys in diverse locations can ensure continued operations if the primarily system is compromised or unavailable. At the network layer, protocols such as the Parallel Redundancy Protocol can be used to simultaneously use redundant and diverse communication over a local network. (Citation: M. Rentschler and H. Heine) [M. Rentschler and H. Heine](https://ieeexplore.ieee.org/document/6505877)

## Detection strategies

- [DET0729 - Detection of Loss of Availability](../../../Defenses/Detection%20Strategies/DET0729%20-%20Detection%20of%20Loss%20of%20Availability.md)

## Sources

- [Colonial Pipeline Company May 2021](https://www.colpipe.com/news/press-releases/media-statement-colonial-pipeline-system-disruption)
- [Corero](https://www.corero.com/resources/files/whitepapers/cns_whitepaper_ics.pdf)
- [Michael J. Assante and Robert M. Lee](https://icscsi.org/library/Documents/White_Papers/SANS%20-%20ICS%20Cyber%20Kill%20Chain.pdf)
- [Tyson Macaulay](https://books.google.com/books?id=oXIYBAAAQBAJ&pg=PA249&lpg=PA249&dq=loss+denial+manipulation+of+view&source=bl&ots=dV1uQ8IUff&sig=ACfU3U2NIwGjhg051D_Ytw6npyEk9xcf4w&hl=en&sa=X&ved=2ahUKEwj2wJ7y4tDlAhVmplkKHSTaDnQQ6AEwAHoECAgQAQ#v=onepage&q=loss%20denial%20manipulation%20of%20view&f=false)
