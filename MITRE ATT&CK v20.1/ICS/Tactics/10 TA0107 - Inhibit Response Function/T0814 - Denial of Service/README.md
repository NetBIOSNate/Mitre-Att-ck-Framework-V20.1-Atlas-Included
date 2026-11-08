# T0814 - Denial of Service

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Adversaries may perform Denial-of-Service (DoS) attacks to disrupt expected device functionality. Examples of DoS attacks include overwhelming the target device with a high volume of requests in a short time period and sending the target device a request it does not know how to handle. Disrupting device state may temporarily render it unresponsive, possibly lasting until a reboot can occur. When placed in this state, devices may be unable to send and receive requests, and may not perform expected response functions in reaction to other events in the environment. 

Some ICS devices are particularly sensitive to DoS events, and may become unresponsive in reaction to even a simple ping sweep. Adversaries may also attempt to execute a Permanent Denial-of-Service (PDoS) against certain devices, such as in the case of the BrickerBot malware. (Citation: ICS-CERT April 2017) 

Adversaries may exploit a software vulnerability to cause a denial of service by taking advantage of a programming error in a program, service, or within the operating system software or kernel itself to execute adversary-controlled code. Vulnerabilities may exist in software that can be used to cause a denial of service condition. 

Adversaries may have prior knowledge about industrial protocols or control devices used in the environment through [Remote System Information Discovery](https://attack.mitre.org/techniques/T0888). There are examples of adversaries remotely causing a [Device Restart/Shutdown](https://attack.mitre.org/techniques/T0816) by exploiting a vulnerability that induces uncontrolled resource consumption. (Citation: ICS-CERT August 2018) (Citation: Common Weakness Enumeration January 2019) (Citation: MITRE March 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0814)

**Tactics**  [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

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

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), power company phone line operators were hit with a denial of service attack so that they couldn’t field customers’ calls about outages. Operators were also denied service to their downstream devices when their serial-to-ethernet converters had their firmware overwritten, which bricked the devices. (Citation: Ukraine15 - EISAC - 201603) [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [S0093 - Backdoor.Oldrea](../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — The [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) payload has caused multiple common OPC platforms to intermittently crash. This could cause a denial of service effect on applications reliant on OPC communications. (Citation: ICS-CERT August 2018) [ICS-CERT August 2018](https://ics-cert.us-cert.gov/advisories/ICSA-14-178-01)
- [S1157 - Fuxnet](../../../Threat%20Intelligence/Software/Malware/S1157%20-%20Fuxnet.md) — [Fuxnet](https://attack.mitre.org/software/S1157) shut down remote access services such as SSH, HTTP, telnet, and SNMP to a device along with deleting the routing table for routing devices to inhibit system accessibility and communication.(Citation: Claroty Fuxnet 2024) [Claroty Fuxnet 2024](https://claroty.com/team82/research/unpacking-the-blackjack-groups-fuxnet-malware)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — The [Industroyer](https://attack.mitre.org/software/S0604) SIPROTEC DoS module exploits the CVE-2015-5374 vulnerability in order to render a Siemens SIPROTEC device unresponsive. Once this vulnerability is successfully exploited, the target device stops responding to any commands until it is rebooted manually. (Citation: Anton Cherepanov, ESET June 2017) Once the tool is executed it sends specifically crafted packets to port 50,000 of the target IP addresses using UDP. The UDP packet contains the following 18 byte payload: 0x11 49 00 00 00 00 00 00 00 00 00 00 00 00 00 00 28 9E. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S1006 - PLC-Blaster](../../../Threat%20Intelligence/Software/Malware/S1006%20-%20PLC-Blaster.md) — The execution on the PLC can be stopped by violating the cycle time limit. The [PLC-Blaster](https://attack.mitre.org/software/S1006) implements an endless loop triggering an error condition within the PLC with the impact of a DoS. (Citation: Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016) [Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016](https://www.blackhat.com/docs/asia-16/materials/asia-16-Spenneberg-PLC-Blaster-A-Worm-Living-Solely-In-The-PLC-wp.pdf)
- [C0031 - Unitronics Defacement Campaign](../../../Threat%20Intelligence/Campaigns/C0031%20-%20Unitronics%20Defacement%20Campaign.md) — During the [Unitronics Defacement Campaign](https://attack.mitre.org/campaigns/C0031), the [CyberAv3ngers](https://attack.mitre.org/groups/G1027) defaced controllers’ [Human-Machine Interface (HMI)](https://attack.mitre.org/assets/A0002), which prevented multiple entities from being able to operate their devices normally.(Citation: CISA AA23-335A IRGC-Affiliated December 2023)(Citation: CISA Unitronics November 2023)(Citation: Jamie Tarabay and Katrina Manson December 2023)(Citation: Frank Bajak and Marc Levy December 2023) Additionally, the [CyberAv3ngers](https://attack.mitre.org/groups/G1027) caused a communications failure in a remote pumping station.(Citation: WPXI Aliquippa Water November 2023) [CISA AA23-335A IRGC-Affiliated December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-335a) · [CISA Unitronics November 2023](https://www.cisa.gov/news-events/alerts/2023/11/28/exploitation-unitronics-plcs-used-water-and-wastewater-systems) · [Frank Bajak and Marc Levy December 2023](https://apnews.com/article/hackers-iran-israel-water-utilities-critical-infrastructure-cisa-554b2aa969c8220016ab2ef94bd7635b) · [Jamie Tarabay and Katrina Manson December 2023](https://www.bloomberg.com/news/articles/2023-12-22/iranian-linked-hacks-expose-failure-to-safeguard-us-water-system) · [WPXI Aliquippa Water November 2023](https://www.wpxi.com/news/local/officials-investigating-cyberattack-municipal-water-authority-aliquippa/K5A3BEW35RAXJPMNHNE35RZ7WA/)

## Detection strategies

- [DET0723 - Detection of Denial of Service](../../../Defenses/Detection%20Strategies/DET0723%20-%20Detection%20of%20Denial%20of%20Service.md)

## Mitigations

- [M0815 - Watchdog Timers](../../../Defenses/Mitigations/M0815%20-%20Watchdog%20Timers.md) — System and process restarts should be performed when a timeout condition occurs.

## Sources

- [Common Weakness Enumeration January 2019](http://cwe.mitre.org/data/definitions/400.html)
- [ICS-CERT April 2017](https://www.us-cert.gov/ics/alerts/ICS-ALERT-17-102-01A)
- [ICS-CERT August 2018](https://ics-cert.us-cert.gov/advisories/ICSA-15-202-01)
- [MITRE March 2018](https://nvd.nist.gov/vuln/detail/CVE-2015-5374)
