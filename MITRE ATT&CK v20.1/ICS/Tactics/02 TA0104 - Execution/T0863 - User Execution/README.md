# T0863 - User Execution

[ICS](../../../README.md) / [Execution](../README.md)

Adversaries may rely on a targeted organizations user interaction for the execution of malicious code. User interaction may consist of installing applications, opening email attachments, or granting higher permissions to documents. 

Adversaries may embed malicious code or visual basic code into files such as Microsoft Word and Excel documents or software installers. (Citation: Booz Allen Hamilton) Execution of this code requires that the user enable scripting or write access within the document. Embedded code may not always be noticeable to the user especially in cases of trojanized software. (Citation: Daavid Hentunen, Antti Tikkanen June 2014) 

A Chinese spearphishing campaign running from December 9, 2011 through February 29, 2012 delivered malware through spearphishing attachments which required user action to achieve execution. (Citation: CISA AA21-201A Pipeline Intrusion July 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0863)

**Tactics**  [Execution](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Mitigations

- [M0949 - Antivirus/Antimalware](../../../Defenses/Mitigations/M0949%20-%20Antivirus%20-%20Antimalware.md) — Ensure anti-virus solution can detect malicious files that allow user execution (e.g., Microsoft Office Macros, program installers).
- [M0945 - Code Signing](../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Prevent the use of unsigned executables, such as installers and scripts.
- [M0938 - Execution Prevention](../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Application control may be able to prevent the running of executables masquerading as other files.
- [M0931 - Network Intrusion Prevention](../../../Defenses/Mitigations/M0931%20-%20Network%20Intrusion%20Prevention.md) — If a link is being visited by a user, network intrusion prevention systems and systems designed to scan and remove malicious downloads can be used to block activity.
- [M0921 - Restrict Web-Based Content](../../../Defenses/Mitigations/M0921%20-%20Restrict%20Web-Based%20Content.md) — If a link is being visited by a user, block unknown or unused files in transit by default that should not be downloaded or by policy from suspicious sites as a best practice to prevent some vectors, such as .scr, .exe, .pif, .cpl, etc. Some download scanning devices can open and analyze compressed and encrypted formats, such as zip and rar that may be used to conceal malicious files.
- [M0917 - User Training](../../../Defenses/Mitigations/M0917%20-%20User%20Training.md) — Use user training as a way to bring awareness to common phishing and spearphishing techniques and how to raise suspicion for potentially malicious events.

## Detection strategies

- [DET0791 - Detection of User Execution](../../../Defenses/Detection%20Strategies/DET0791%20-%20Detection%20of%20User%20Execution.md)

## Targeted assets

- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [S0093 - Backdoor.Oldrea](../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — Execution of [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) relies on a user opening a trojanized installer attached to an email. (Citation: Daavid Hentunen, Antti Tikkanen June 2014) (Citation: Kyle Wilhoit) [Daavid Hentunen, Antti Tikkanen June 2014](https://www.f-secure.com/weblog/archives/00002718.html) · [Kyle Wilhoit](https://www.youtube.com/watch?v=eywmb7UDODY&feature=youtu.be&t=939)
- [S0606 - Bad Rabbit](../../../Threat%20Intelligence/Software/Malware/S0606%20-%20Bad%20Rabbit.md) — [Bad Rabbit](https://attack.mitre.org/software/S0606) is disguised as an Adobe Flash installer. When the file is opened it starts locking the infected computer. (Citation: Orkhan Mamedov, Fedor Sinitsyn, Anton Ivanov October 2017) [Orkhan Mamedov, Fedor Sinitsyn, Anton Ivanov October 2017](https://securelist.com/bad-rabbit-ransomware/82851/)
- [S0496 - REvil](../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) initially executes when the user clicks on a JavaScript file included in the phishing emails .zip attachment. (Citation: Tom Fakterman August 2019) [Tom Fakterman August 2019](https://www.cybereason.com/blog/the-sodinokibi-ransomware-attack)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) infects DLL's associated with the WinCC Simatic manager which are responsible for opening project files. If a user opens an uninfected project file using a compromised manager, the file will be infected with Stuxnet code. If an infected project is opened with the Simatic manager, the modified data file will trigger a search for the `xyz.dll` file. If the `xyz.dll` file is not found in any of the specified locations, the malicious DLL will be loaded and executed by the manager. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Sources

- [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf)
- [Daavid Hentunen, Antti Tikkanen June 2014](https://www.f-secure.com/weblog/archives/00002718.html)
- [CISA AA21-201A Pipeline Intrusion July 2021](https://us-cert.cisa.gov/sites/default/files/publications/AA21-201A_Chinese_Gas_Pipeline_Intrusion_Campaign_2011_to_2013%20%281%29.pdf)
