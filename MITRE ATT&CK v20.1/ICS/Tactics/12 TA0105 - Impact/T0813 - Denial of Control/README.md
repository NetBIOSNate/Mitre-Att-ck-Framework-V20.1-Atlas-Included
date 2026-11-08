# T0813 - Denial of Control

[ICS](../../../README.md) / [Impact](../README.md)

Adversaries may cause a denial of control to temporarily prevent operators and engineers from interacting with process controls. An adversary may attempt to deny process control access to cause a temporary loss of communication with the control device or to prevent operator adjustment of process controls. An affected process may still be operating during the period of control loss, but not necessarily in a desired state. (Citation: Corero) (Citation: Michael J. Assante and Robert M. Lee) (Citation: Tyson Macaulay)

In the 2017 Dallas Siren incident operators were unable to disable the false alarms from the Office of Emergency Management headquarters. (Citation: Mark Loveless April 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0813)

**Tactics**  [Impact](../README.md)

**Platforms**  [No platform specified](../../../Platforms/None.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [KillDisk](https://attack.mitre.org/software/S0607) rendered devices that were necessary for remote recovery unusable, including at least one RTU. Additionally, [Sandworm Team](https://attack.mitre.org/groups/G0034) overwrote the firmware for serial-to-ethernet converters, denying operators control of the downstream devices. (Citation: Booz Allen Hamilton)(Citation: Ukraine15 - EISAC - 201603) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf) · [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [C0066 - 2026 U.S. Water Utilities Attacks](../../../Threat%20Intelligence/Campaigns/C0066%20-%202026%20U.S.%20Water%20Utilities%20Attacks.md) — During the [2026 U.S. Water Utilities Attacks](https://attack.mitre.org/campaigns/C0066), the adversary denied operators the ability to control their systems by shutting down and disabling computerized water plant controls via malware over a wireless connection.(Citation: Tenable Minnesota Water Utilities)(Citation: Forescout Water Systems Attack)(Citation: Dragos Water Under Attack) [Dragos Water Under Attack](https://www.dragos.com/blog/water-utility-attacks-decade-of-gaps) · [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know) · [Forescout Water Systems Attack](https://www.forescout.com/blog/ot-security-analysis-exposed-devices-attacked-in-us-water-systems/)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604) is able to block serial COM channels temporarily causing a denial of control. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [C0020 - Maroochy Water Breach](../../../Threat%20Intelligence/Campaigns/C0020%20-%20Maroochy%20Water%20Breach.md) — In the [Maroochy Water Breach](https://attack.mitre.org/campaigns/C0020), the adversary temporarily shut an investigator out of the network preventing them from issuing any controls.(Citation: Marshall Abrams July 2008) [Marshall Abrams July 2008](https://www.mitre.org/sites/default/files/pdf/08_1145.pdf)

## Mitigations

- [M0953 - Data Backup](../../../Defenses/Mitigations/M0953%20-%20Data%20Backup.md) — Take and store data backups from end user systems and critical servers. Ensure backup and storage systems are hardened and kept separate from the corporate network to prevent compromise. Maintain and exercise incident response plans (Citation: Department of Homeland Security October 2009), including the management of gold-copy back-up images and configurations for key systems to enable quick recovery and response from adversarial activities that impact control, view, or availability. [Department of Homeland Security October 2009](https://us-cert.cisa.gov/sites/default/files/recommended_practices/final-RP_ics_cybersecurity_incident_response_100609.pdf)
- [M0810 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Provide operators with redundant, out-of-band communication to support monitoring and control of the operational processes, especially when recovering from a network outage (Citation: National Institute of Standards and Technology April 2013). Out-of-band communication should utilize diverse systems and technologies to minimize common failure modes and vulnerabilities within the communications infrastructure. For example, wireless networks (e.g., 3G, 4G) can be used to provide diverse and redundant delivery of data. [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0811 - Redundancy of Service](../../../Defenses/Mitigations/M0811%20-%20Redundancy%20of%20Service.md) — Hot-standbys in diverse locations can ensure continued operations if the primarily system are compromised or unavailable. At the network layer, protocols such as the Parallel Redundancy Protocol can be used to simultaneously use redundant and diverse communication over a local network. (Citation: M. Rentschler and H. Heine) [M. Rentschler and H. Heine](https://ieeexplore.ieee.org/document/6505877)

## Detection strategies

- [DET0786 - Detection of Denial of Control](../../../Defenses/Detection%20Strategies/DET0786%20-%20Detection%20of%20Denial%20of%20Control.md)

## Sources

- [Corero](https://www.corero.com/resources/files/whitepapers/cns_whitepaper_ics.pdf)
- [Mark Loveless April 2017](https://duo.com/decipher/the-dallas-county-siren-hack)
- [Michael J. Assante and Robert M. Lee](https://icscsi.org/library/Documents/White_Papers/SANS%20-%20ICS%20Cyber%20Kill%20Chain.pdf)
- [Tyson Macaulay](https://books.google.com/books?id=oXIYBAAAQBAJ&pg=PA249&lpg=PA249&dq=loss+denial+manipulation+of+view&source=bl&ots=dV1uQ8IUff&sig=ACfU3U2NIwGjhg051D_Ytw6npyEk9xcf4w&hl=en&sa=X&ved=2ahUKEwj2wJ7y4tDlAhVmplkKHSTaDnQQ6AEwAHoECAgQAQ#v=onepage&q=loss%20denial%20manipulation%20of%20view&f=false)
