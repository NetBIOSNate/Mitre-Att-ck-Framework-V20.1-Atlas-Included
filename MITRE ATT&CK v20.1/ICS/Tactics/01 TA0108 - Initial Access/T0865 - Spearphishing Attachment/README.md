# T0865 - Spearphishing Attachment

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may use a spearphishing attachment, a variant of spearphishing, as a form of a social engineering attack against specific targets. Spearphishing attachments are different from other forms of spearphishing in that they employ malware attached to an email. All forms of spearphishing are electronically delivered and target a specific individual, company, or industry. In this scenario, adversaries attach a file to the spearphishing email and usually rely upon [User Execution](https://attack.mitre.org/techniques/T0863) to gain execution and access. (Citation: Enterprise ATT&CK October 2019) 

A Chinese spearphishing campaign running from December 9, 2011 through February 29, 2012, targeted ONG organizations and their employees. The emails were constructed with a high level of sophistication to convince employees to open the malicious file attachments. (Citation: CISA AA21-201A Pipeline Intrusion July 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0865)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Targeted assets

- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [G1000 - ALLANITE](../../../Threat%20Intelligence/Groups/G1000%20-%20ALLANITE.md) — [ALLANITE](https://attack.mitre.org/groups/G1000) utilized spear phishing to gain access into energy sector environments. (Citation: Jeff Jones May 2018) [Jeff Jones May 2018](https://www.eisac.com/public-news-detail?id=115909)
- [G0064 - APT33](../../../Threat%20Intelligence/Groups/G0064%20-%20APT33.md) — [APT33](https://attack.mitre.org/groups/G0064) sent spear phishing emails containing links to HTML application files, which were embedded with malicious code. (Citation: Jacqueline O'Leary et al. September 2017) [APT33](https://attack.mitre.org/groups/G0064) has conducted targeted spear phishing campaigns against U.S. government agencies and private sector companies. (Citation: Andy Greenburg June 2019) [Andy Greenburg June 2019](https://www.wired.com/story/iran-hackers-us-phishing-tensions/) · [Jacqueline O'Leary et al. September 2017](https://www.fireeye.com/blog/threat-research/2017/09/apt33-insights-into-iranian-cyber-espionage.html)
- [S0093 - Backdoor.Oldrea](../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — The [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) RAT is distributed through a trojanized installer attached to emails. (Citation: Daavid Hentunen, Antti Tikkanen June 2014) [Daavid Hentunen, Antti Tikkanen June 2014](https://www.f-secure.com/weblog/archives/00002718.html)
- [S0089 - BlackEnergy](../../../Threat%20Intelligence/Software/Malware/S0089%20-%20BlackEnergy.md) — [BlackEnergy](https://attack.mitre.org/software/S0089) targeted energy sector organizations in a wide reaching email spearphishing campaign. Adversaries utilized malicious Microsoft Word documents attachments. (Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf)
- [G0032 - Lazarus Group](../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) has been observed targeting organizations using spearphishing documents with embedded malicious payloads. (Citation: Novetta Threat Research Group February 2016) Highly targeted spear phishing campaigns have been conducted against a U.S. electric grid company. (Citation: Eduard Kovacs March 2018) [Eduard Kovacs March 2018](https://www.securityweek.com/five-threat-groups-target-industrial-systems-dragos) · [Novetta Threat Research Group February 2016](https://web.archive.org/web/20220707091904/https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf)
- [G0049 - OilRig](../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) used spearphishing emails with malicious Microsoft Excel spreadsheet attachments. (Citation: Robert Falcone, Bryan Lee May 2016) [Robert Falcone, Bryan Lee May 2016](https://unit42.paloaltonetworks.com/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/)

## Detection strategies

- [DET0781 - Detection of Spearphishing Attachment](../../../Defenses/Detection%20Strategies/DET0781%20-%20Detection%20of%20Spearphishing%20Attachment.md)

## Mitigations

- [M0949 - Antivirus/Antimalware](../../../Defenses/Mitigations/M0949%20-%20Antivirus%20-%20Antimalware.md) — Deploy anti-virus on all systems that support external email.
- [M0931 - Network Intrusion Prevention](../../../Defenses/Mitigations/M0931%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion prevention systems and systems designed to scan and remove malicious email attachments can be used to block activity.
- [M0921 - Restrict Web-Based Content](../../../Defenses/Mitigations/M0921%20-%20Restrict%20Web-Based%20Content.md) — Consider restricting access to email within critical process environments. Additionally, downloads and attachments may be disabled if email is still necessary.
- [M0917 - User Training](../../../Defenses/Mitigations/M0917%20-%20User%20Training.md) — Users can be trained to identify social engineering techniques and spearphishing emails.

## Sources

- [CISA AA21-201A Pipeline Intrusion July 2021](https://us-cert.cisa.gov/sites/default/files/publications/AA21-201A_Chinese_Gas_Pipeline_Intrusion_Campaign_2011_to_2013%20%281%29.pdf)
- [Enterprise ATT&CK October 2019](https://attack.mitre.org/techniques/T1193/)
