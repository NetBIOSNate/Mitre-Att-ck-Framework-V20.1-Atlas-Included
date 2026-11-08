# T0882 - Theft of Operational Information

[ICS](../../../README.md) / [Impact](../README.md)

Adversaries may steal operational information on a production environment as a direct mission outcome for personal gain or to inform future operations. This information may include design documents, schedules, rotational data, or similar artifacts that provide insight on operations.    In the Bowman Dam incident, adversaries probed systems for operational data. (Citation: Mark Thompson March 2016) (Citation: Danny Yadron December 2015)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0882)

**Tactics**  [Impact](../README.md)

**Platforms**  [No platform specified](../../../Platforms/None.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries stole sensitive operational information that was used to plan the attack on the operational technology systems.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S1000 - ACAD/Medre.A](../../../Threat%20Intelligence/Software/Malware/S1000%20-%20ACAD%20-%20Medre.A.md) — [ACAD/Medre.A](https://attack.mitre.org/software/S1000) can collect AutoCad files with drawings. These drawings may contain operational information. (Citation: ESET) [ESET](https://www.welivesecurity.com/wp-content/uploads/200x/white-papers/ESET_ACAD_Medre_A_whitepaper.pdf)
- [S0038 - Duqu](../../../Threat%20Intelligence/Software/Malware/S0038%20-%20Duqu.md) — [Duqu](https://attack.mitre.org/software/S0038)'s purpose is to gather intelligence data and assets from entities such as industrial infrastructure and system manufacturers, amongst others not in the industrial sector, in order to more easily conduct a future attack against another third party.(Citation: Symantec W32.Duqu) [Symantec W32.Duqu](https://web.archive.org/web/20111213083345/https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf)
- [S0143 - Flame](../../../Threat%20Intelligence/Software/Malware/S0143%20-%20Flame.md) — [Flame](https://attack.mitre.org/software/S0143) can collect AutoCAD design data and visio diagrams as well as other documents that may contain operational information. (Citation: Kevin Savage and Branko Spasojevic) [Kevin Savage and Branko Spasojevic](https://web.archive.org/web/20190930124504/https:/www.symantec.com/security-center/writeup/2012-052811-0308-99)
- [S0496 - REvil](../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) sends exfiltrated data from the victims system using HTTPS POST messages sent to the C2 system. (Citation: McAfee Labs October 2019) (Citation: SecureWorks September 2019) [McAfee Labs October 2019](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/mcafee-atr-analyzes-sodinokibi-aka-revil-ransomware-as-a-service-what-the-code-tells-us) · [SecureWorks September 2019](https://www.secureworks.com/research/revil-sodinokibi-ransomware)

## Mitigations

- [M0803 - Data Loss Prevention](../../../Defenses/Mitigations/M0803%20-%20Data%20Loss%20Prevention.md) — Apply DLP to protect the confidentiality of information related to operational processes, facility locations, device configurations, programs, or databases that may have information that can be used to infer organizational trade-secrets, recipes, and other intellectual property (IP).
- [M0941 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M0941%20-%20Encrypt%20Sensitive%20Information.md) — Encrypt any operational data with strong confidentiality requirements, including organizational trade-secrets, recipes, and other intellectual property (IP).
- [M0809 - Operational Information Confidentiality](../../../Defenses/Mitigations/M0809%20-%20Operational%20Information%20Confidentiality.md) — Example mitigations could include minimizing its distribution/storage or obfuscating the information (e.g., facility coverterms, codenames). In many cases this information may be necessary to support critical engineering, maintenance, or operational functions, therefore, it may not be feasible to implement.
- [M0922 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Protect files stored locally with proper permissions to limit opportunities for adversaries to interact and collect information from databases. (Citation: Keith Stouffer May 2015) (Citation: National Institute of Standards and Technology April 2013) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)

## Detection strategies

- [DET0732 - Detection of Theft of Operational Information](../../../Defenses/Detection%20Strategies/DET0732%20-%20Detection%20of%20Theft%20of%20Operational%20Information.md)

## Sources

- [Danny Yadron December 2015](https://www.wsj.com/articles/iranian-hackers-infiltrated-new-york-dam-in-2013-1450662559)
- [Mark Thompson March 2016](https://time.com/4270728/iran-cyber-attack-dam-fbi/)
