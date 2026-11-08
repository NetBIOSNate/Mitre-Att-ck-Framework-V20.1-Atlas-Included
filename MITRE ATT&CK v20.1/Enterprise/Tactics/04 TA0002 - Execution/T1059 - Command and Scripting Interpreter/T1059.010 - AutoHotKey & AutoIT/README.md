# T1059.010 - AutoHotKey & AutoIT

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1059 - Command and Scripting Interpreter](../README.md)

Adversaries may execute commands and perform malicious tasks using AutoIT and AutoHotKey automation scripts. AutoIT and AutoHotkey (AHK) are scripting languages that enable users to automate Windows tasks. These automation scripts can be used to perform a wide variety of actions, such as clicking on buttons, entering text, and opening and closing programs.(Citation: AutoIT)(Citation: AutoHotKey)

Adversaries may use AHK (`.ahk`) and AutoIT (`.au3`) scripts to execute malicious code on a victim's system. For example, adversaries have used for AHK to execute payloads and other modular malware such as keyloggers. Adversaries have also used custom AHK files containing embedded malware as [Phishing](https://attack.mitre.org/techniques/T1566) payloads.(Citation: Splunk DarkGate)

These scripts may also be compiled into self-contained executable payloads (`.exe`).(Citation: AutoIT)(Citation: AutoHotKey)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1059/010)

**Tactics**  [Execution](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0087 - APT39](../../../../Threat%20Intelligence/Groups/G0087%20-%20APT39.md) — [APT39](https://attack.mitre.org/groups/G0087) has utilized AutoIt malware scripts embedded in Microsoft Office documents or malicious links.(Citation: FBI FLASH APT39 September 2020) [FBI FLASH APT39 September 2020](https://www.iranwatch.org/sites/default/files/public-intelligence-alert.pdf)
- [S1111 - DarkGate](../../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) uses AutoIt scripts dropped to a hidden directory during initial installation phases, such as `test.au3`.(Citation: Ensilo Darkgate 2018) [Ensilo Darkgate 2018](https://www.fortinet.com/blog/threat-research/enter-the-darkgate-new-cryptocurrency-mining-and-ransomware-campaign)
- [S1213 - Lumma Stealer](../../../../Threat%20Intelligence/Software/Malware/S1213%20-%20Lumma%20Stealer.md) — [Lumma Stealer](https://attack.mitre.org/software/S1213) has utilized AutoIt malware scripts and AutoIt executables.(Citation: Qualys LummaStealer 2024)(Citation: Cybereason LumaStealer Undated) [Cybereason LumaStealer Undated](https://www.cybereason.com/blog/threat-analysis-rise-of-lummastealer) · [Qualys LummaStealer 2024](https://blog.qualys.com/vulnerabilities-threat-research/2024/10/20/unmasking-lumma-stealer-analyzing-deceptive-tactics-with-fake-captcha)
- [S0530 - Melcoz](../../../../Threat%20Intelligence/Software/Malware/S0530%20-%20Melcoz.md) — [Melcoz](https://attack.mitre.org/software/S0530) has been distributed through an AutoIt loader script.(Citation: Securelist Brazilian Banking Malware July 2020) [Securelist Brazilian Banking Malware July 2020](https://securelist.com/the-tetrade-brazilian-banking-malware/97779/)
- [S1017 - OutSteel](../../../../Threat%20Intelligence/Software/Malware/S1017%20-%20OutSteel.md) — [OutSteel](https://attack.mitre.org/software/S1017) was developed using the AutoIT scripting language.(Citation: Palo Alto Unit 42 OutSteel SaintBot February 2022 ) [Palo Alto Unit 42 OutSteel SaintBot February 2022 ](https://unit42.paloaltonetworks.com/ukraine-targeted-outsteel-saintbot/)
- [S1207 - XLoader](../../../../Threat%20Intelligence/Software/Malware/S1207%20-%20XLoader.md) — [XLoader](https://attack.mitre.org/software/S1207) can use an AutoIT script to decrypt a payload file, load it into victim memory, then execute it on the victim machine.(Citation: Google XLoader 2017) [Google XLoader 2017](https://cloud.google.com/blog/topics/threat-intelligence/formbook-malware-distribution-campaigns/)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control to prevent execution of `AutoIt3.exe`, `AutoHotkey.exe`, and other related features that may not be required for a given system or network to prevent potential misuse by adversaries.

## Detection strategies

- [DET0332 - Detection Strategy for AutoHotKey & AutoIT Abuse](../../../../Defenses/Detection%20Strategies/DET0332%20-%20Detection%20Strategy%20for%20AutoHotKey%20%26%20AutoIT%20Abuse.md)

## Sources

- [AutoHotKey](https://www.autohotkey.com/docs/v1/Program.htm)
- [AutoIT](https://www.autoitscript.com/autoit3/docs/intro/running.htm)
- [Splunk DarkGate](https://www.splunk.com/en_us/blog/security/enter-the-gates-an-analysis-of-the-darkgate-autoit-loader.html)
