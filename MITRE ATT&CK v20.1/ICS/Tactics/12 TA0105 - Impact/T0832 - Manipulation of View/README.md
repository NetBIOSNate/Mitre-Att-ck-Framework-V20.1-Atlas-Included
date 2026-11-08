# T0832 - Manipulation of View

[ICS](../../../README.md) / [Impact](../README.md)

Adversaries may attempt to manipulate the information reported back to operators or controllers. This manipulation may be short term or sustained. During this time the process itself could be in a much different state than what is reported. (Citation: Corero) (Citation: Michael J. Assante and Robert M. Lee) (Citation: Tyson Macaulay) 

Operators may be fooled into doing something that is harmful to the system in a loss of view situation. With a manipulated view into the systems, operators may issue inappropriate control sequences that introduce faults or catastrophic failures into the system. Business analysis systems can also be provided with inaccurate data leading to bad management decisions.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0832)

**Tactics**  [Impact](../README.md)

**Platforms**  [No platform specified](../../../Platforms/None.md)

## Detection strategies

- [DET0785 - Detection of Manipulation of View](../../../Defenses/Detection%20Strategies/DET0785%20-%20Detection%20of%20Manipulation%20of%20View.md)

## Mitigations

- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for control functions should provide authenticity through MAC functions or digital signatures. If not, utilize bump-in-the-wire devices or VPNs to enforce communication authenticity between devices that are not capable of supporting this (e.g., legacy controllers, RTUs).
- [M0953 - Data Backup](../../../Defenses/Mitigations/M0953%20-%20Data%20Backup.md) — Take and store data backups from end user systems and critical servers. Ensure backup and storage systems are hardened and kept separate from the corporate network to prevent compromise. Maintain and exercise incident response plans (Citation: Department of Homeland Security October 2009), including the management of gold-copy back-up images and configurations for key systems to enable quick recovery and response from adversarial activities that impact control, view, or availability. [Department of Homeland Security October 2009](https://us-cert.cisa.gov/sites/default/files/recommended_practices/final-RP_ics_cybersecurity_incident_response_100609.pdf)
- [M0810 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Utilize out-of-band communication to validate the integrity of data from the primary channel.

## Procedure examples

- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604)'s OPC module can brute force values and will send out a 0x01 status which for the target systems equates to a Primary Variable Out of Limits misdirecting operators from understanding protective relay status. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) manipulates the view of operators replaying process input and manipulating the I/O image to evade detection and inhibit protection functions. (Citation: Langer Stuxnet) (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en) · [Langer Stuxnet](https://www.langner.com/wp-content/uploads/2017/03/to-kill-a-centrifuge.pdf)

## Sources

- [Corero](https://www.corero.com/resources/files/whitepapers/cns_whitepaper_ics.pdf)
- [Michael J. Assante and Robert M. Lee](https://icscsi.org/library/Documents/White_Papers/SANS%20-%20ICS%20Cyber%20Kill%20Chain.pdf)
- [Tyson Macaulay](https://books.google.com/books?id=oXIYBAAAQBAJ&pg=PA249&lpg=PA249&dq=loss+denial+manipulation+of+view&source=bl&ots=dV1uQ8IUff&sig=ACfU3U2NIwGjhg051D_Ytw6npyEk9xcf4w&hl=en&sa=X&ved=2ahUKEwj2wJ7y4tDlAhVmplkKHSTaDnQQ6AEwAHoECAgQAQ#v=onepage&q=loss%20denial%20manipulation%20of%20view&f=false)
