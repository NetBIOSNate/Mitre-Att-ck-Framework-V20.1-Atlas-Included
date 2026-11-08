# T0811 - Data from Information Repositories

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may target and collect data from information repositories. This can include sensitive data such as specifications, schematics, or diagrams of control system layouts, devices, and processes. Examples of information repositories include reference databases in the process environment, as well as databases in the corporate network that might contain information about the ICS.(Citation: Cybersecurity & Infrastructure Security Agency March 2018)

Information collected from these systems may provide the adversary with a better understanding of the operational environment, vendors used, processes, or procedures of the ICS.

In a campaign between 2011 and 2013 against ONG organizations, Chinese state-sponsored actors searched document repositories for specific information such as, system manuals, remote terminal unit (RTU) sites, personnel lists, documents that included the string SCAD*, user credentials, and remote dial-up access information. (Citation: CISA AA21-201A Pipeline Intrusion July 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0811)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Detection strategies

- [DET0754 - Detection of Data from Information Repositories](../../../Defenses/Detection%20Strategies/DET0754%20-%20Detection%20of%20Data%20from%20Information%20Repositories.md)

## Targeted assets

- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)

## Mitigations

- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Consider periodic reviews of accounts and privileges for critical and sensitive repositories.
- [M0941 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M0941%20-%20Encrypt%20Sensitive%20Information.md) — Information which is sensitive to the operation and architecture of the process environment may be encrypted to ensure confidentiality and restrict access to only those who need to know. (Citation: Keith Stouffer May 2015) (Citation: National Institute of Standards and Technology April 2013) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0926 - Privileged Account Management](../../../Defenses/Mitigations/M0926%20-%20Privileged%20Account%20Management.md) — Minimize permissions and access for service accounts to limit the information that may be exposed or collected by malicious users or software. (Citation: National Institute of Standards and Technology April 2013) [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0922 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Protect files with proper permissions to limit opportunities for adversaries to interact and collect information from databases. (Citation: Keith Stouffer May 2015) (Citation: National Institute of Standards and Technology April 2013) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0918 - User Account Management](../../../Defenses/Mitigations/M0918%20-%20User%20Account%20Management.md) — Ensure users and user groups have appropriate permissions for their roles through Identity and Access Management (IAM) controls to prevent misuse. Implement user accounts for each individual that may access the repositories for role enforcement and non-repudiation of actions.
- [M0917 - User Training](../../../Defenses/Mitigations/M0917%20-%20User%20Training.md) — Develop and publish policies that define acceptable information to be stored in repositories.

## Procedure examples

- [S0038 - Duqu](../../../Threat%20Intelligence/Software/Malware/S0038%20-%20Duqu.md) — [Duqu](https://attack.mitre.org/software/S0038) downloads additional modules for the collection of data in information repositories, including the Infostealer 2 module that can access data from Windows Shares.(Citation: Symantec W32.Duqu) [Symantec W32.Duqu](https://web.archive.org/web/20111213083345/https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf)

## Sources

- [Cybersecurity & Infrastructure Security Agency March 2018](https://us-cert.cisa.gov/ncas/alerts/TA18-074A)
- [CISA AA21-201A Pipeline Intrusion July 2021](https://us-cert.cisa.gov/sites/default/files/publications/AA21-201A_Chinese_Gas_Pipeline_Intrusion_Campaign_2011_to_2013%20%281%29.pdf)
