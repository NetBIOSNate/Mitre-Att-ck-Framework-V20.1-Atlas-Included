# T0893 - Data from Local System

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may target and collect data from local system sources, such as file systems, configuration files, or local databases. This can include sensitive data such as specifications, schematics, or diagrams of control system layouts, devices, and processes.

Adversaries may do this using [Command-Line Interface](https://attack.mitre.org/techniques/T0807) or [Scripting](https://attack.mitre.org/techniques/T0853) techniques to interact with the file system to gather information. Adversaries may also use [Automated Collection](https://attack.mitre.org/techniques/T0802) on the local system.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0893)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Mitigations

- [M0803 - Data Loss Prevention](../../../Defenses/Mitigations/M0803%20-%20Data%20Loss%20Prevention.md) — Data loss prevention can restrict access to sensitive data and detect sensitive data that is unencrypted.
- [M0941 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M0941%20-%20Encrypt%20Sensitive%20Information.md) — Information which is sensitive to the operation and architecture of the process environment may be encrypted to ensure confidentiality and restrict access to only those who need to know. (Citation: Keith Stouffer May 2015) (Citation: National Institute of Standards and Technology April 2013) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0922 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Protect files stored locally with proper permissions to limit opportunities for adversaries to interact and collect information from the local system. (Citation: Keith Stouffer May 2015) (Citation: National Institute of Standards and Technology April 2013) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0917 - User Training](../../../Defenses/Mitigations/M0917%20-%20User%20Training.md) — Develop and publish policies that define acceptable information to be stored on local systems.

## Procedure examples

- [S1000 - ACAD/Medre.A](../../../Threat%20Intelligence/Software/Malware/S1000%20-%20ACAD%20-%20Medre.A.md) — [ACAD/Medre.A](https://attack.mitre.org/software/S1000) collects information related to the AutoCAD application. The worm collects AutoCAD (*.dwg) files with drawings from infected systems. (Citation: ESET) [ESET](https://www.welivesecurity.com/wp-content/uploads/200x/white-papers/ESET_ACAD_Medre_A_whitepaper.pdf)
- [S0038 - Duqu](../../../Threat%20Intelligence/Software/Malware/S0038%20-%20Duqu.md) — [Duqu](https://attack.mitre.org/software/S0038) downloads additional modules for the collection of data from local systems. The modules are named: infostealer 1, infostealer 2 and reconnaissance.(Citation: Symantec W32.Duqu) [Symantec W32.Duqu](https://web.archive.org/web/20111213083345/https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf)
- [S0143 - Flame](../../../Threat%20Intelligence/Software/Malware/S0143%20-%20Flame.md) — [Flame](https://attack.mitre.org/software/S0143) has built-in modules to gather information from compromised computers. (Citation: Kevin Savage and Branko Spasojevic) [Kevin Savage and Branko Spasojevic](https://web.archive.org/web/20190930124504/https:/www.symantec.com/security-center/writeup/2012-052811-0308-99)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0749 - Detection of Data from Local System](../../../Defenses/Detection%20Strategies/DET0749%20-%20Detection%20of%20Data%20from%20Local%20System.md)
