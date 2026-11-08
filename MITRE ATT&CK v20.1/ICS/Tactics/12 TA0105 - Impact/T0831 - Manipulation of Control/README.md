# T0831 - Manipulation of Control

[ICS](../../../README.md) / [Impact](../README.md)

Adversaries may manipulate physical process control within the industrial environment. Methods of manipulating control can include changes to set point values, tags, or other parameters. Adversaries may manipulate control systems devices or possibly leverage their own, to communicate with and command physical control processes. The duration of manipulation may be temporary or longer sustained, depending on operator detection.   

Methods of Manipulation of Control include: 

* Man-in-the-middle  
* Spoof command message 
* Changing setpoints  

A Polish student used a remote controller device to interface with the Lodz city tram system in Poland. (Citation: John Bill May 2017) (Citation: Shelley Smith February 2008) (Citation: Bruce Schneier January 2008) Using this remote, the student was able to capture and replay legitimate tram signals. As a consequence, four trams were derailed and twelve people injured due to resulting emergency stops. (Citation: Shelley Smith February 2008) The track controlling commands issued may have also resulted in tram collisions, a further risk to those on board and nearby the areas of impact. (Citation: Bruce Schneier January 2008)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0831)

**Tactics**  [Impact](../README.md)

**Platforms**  [No platform specified](../../../Platforms/None.md)

## Detection strategies

- [DET0747 - Detection of Manipulation of Control](../../../Defenses/Detection%20Strategies/DET0747%20-%20Detection%20of%20Manipulation%20of%20Control.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) opened live breakers via remote commands to the HMI, causing blackouts. (Citation: Ukraine15 - EISAC - 201603) [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604) toggles breakers to the open state utilizing unauthorized command messages. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) can reprogram a PLC and change critical parameters in such a way that legitimate commands can be overridden or intercepted. In addition, Stuxnet can apply inappropriate command sequences or parameters to cause damage to property. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Mitigations

- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for control functions should provide authenticity through MAC functions or digital signatures. If not, utilize bump-in-the-wire devices or VPNs to enforce communication authenticity between devices that are not capable of supporting this (e.g., legacy controllers, RTUs).
- [M0953 - Data Backup](../../../Defenses/Mitigations/M0953%20-%20Data%20Backup.md) — Take and store data backups from end user systems and critical servers. Ensure backup and storage systems are hardened and kept separate from the corporate network to prevent compromise. Maintain and exercise incident response plans (Citation: Department of Homeland Security October 2009), including the management of gold-copy back-up images and configurations for key systems to enable quick recovery and response from adversarial activities that impact control, view, or availability. [Department of Homeland Security October 2009](https://us-cert.cisa.gov/sites/default/files/recommended_practices/final-RP_ics_cybersecurity_incident_response_100609.pdf)
- [M0810 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Utilize out-of-band communication to validate the integrity of data from the primary channel.

## Sources

- [Bruce Schneier January 2008](https://www.schneier.com/blog/archives/2008/01/hacking_the_pol.html)
- [John Bill May 2017](https://www.londonreconnections.com/2017/hacked-cyber-security-railways/)
- [Shelley Smith February 2008](https://inhomelandsecurity.com/teen_hacker_in_poland_plays_tr/)
